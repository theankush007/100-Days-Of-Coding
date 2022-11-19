import java.util.Collections;
import java.util.HashSet;
import java.util.List;
import java.util.Map;
import java.util.Scanner;
import java.util.Set;
import java.util.stream.IntStream;
import java.util.stream.Stream;

import static java.util.stream.Collectors.groupingBy;
import static java.util.stream.Collectors.mapping;
import static java.util.stream.Collectors.toList;
import static java.util.stream.Collectors.toSet;

enum Color {
    RED,
    GREEN
}

final class TreeNode {
    private final int value;
    private final Color color;
    private final List<TreeNode> children;

    public TreeNode(int value, Color color, List<TreeNode> children) {
        this.value = value;
        this.color = color;
        this.children = children == null ? Collections.emptyList() : Collections.unmodifiableList(children);
    }

    public int getValue() {
        return this.value;
    }

    public Color getColor() {
        return this.color;
    }

    public List<TreeNode> getChildren() {
        return this.children;
    }
}

interface TreeVisitor {
    void visit(TreeNode node, int depth);

    int getResult();

    static void visitGraph(TreeNode root, TreeVisitor visitor) {
        visitGraph(root, visitor, 0);
    }

    private static void visitGraph(TreeNode node, TreeVisitor visitor, int depth) {
        if (node == null) {
            return;
        }
        visitor.visit(node, depth);
        final int childDepth = depth + 1;
        node.getChildren().forEach(treeNode -> visitGraph(treeNode, visitor, childDepth));
    }
}

class SumInLeavesVisitor implements TreeVisitor {
    private int sum;

    @Override
    public void visit(TreeNode node, int depth) {
        if (node.getChildren().isEmpty()) {
            this.sum += node.getValue();
        }
    }

    @Override
    public int getResult() {
        return this.sum;
    }
}

class ProductOfRedNodesVisitor implements TreeVisitor {
    private long product = 1;

    @Override
    public void visit(TreeNode node, int depth) {
        if (node.getColor() == Color.RED) {
            this.product = this.product * node.getValue() % 1_000_000_007;
        }
    }

    @Override
    public int getResult() {
        return (int) this.product;
    }
}

class FancyVisitor implements TreeVisitor {
    private int sum;

    @Override
    public void visit(TreeNode node, int depth) {
        if (node.getChildren().isEmpty()) {
            if (node.getColor() == Color.GREEN) {
                this.sum += node.getValue();
            }
        } else if (depth % 2 == 0) {
            this.sum -= node.getValue();
        }
    }

    @Override
    public int getResult() {
        return Math.abs(this.sum);
    }
}

public class Solution {
    public static TreeNode readInput() {
        try (final Scanner scanner = new Scanner(System.in)) {
            final int n = scanner.nextInt();
            final int[] values = IntStream.generate(scanner::nextInt)
                    .limit(n)
                    .toArray();
            final Color[] colors = IntStream.generate(scanner::nextInt)
                    .limit(n)
                    .mapToObj(i -> i % 2 == 0 ? Color.RED : Color.GREEN)
                    .toArray(Color[]::new);
            final Map<Integer, Set<Integer>> edges =
                    Stream.generate(() -> new int[]{scanner.nextInt() - 1, scanner.nextInt() - 1})
                            .limit(n - 1)
                            .flatMap(x -> Stream.of(x, new int[]{x[1], x[0]}))
                            .collect(groupingBy(x -> x[0], mapping(x -> x[1], toSet())));

            class TreeBuilder {
                TreeNode build(int parentIndex, int index) {
                    final List<TreeNode> children = edges.computeIfAbsent(index, HashSet::new)
                            .stream()
                            .filter(x -> x != parentIndex)
                            .map(x -> this.build(index, x))
                            .collect(toList());
                    return new TreeNode(values[index], colors[index], children);
                }
            }
            return new TreeBuilder().build(-1, 0);
        }
    }

    public static void main(String[] args) {
        final TreeNode root = readInput();

        Stream.of(new SumInLeavesVisitor(), new ProductOfRedNodesVisitor(), new FancyVisitor())
                .peek(visitor -> TreeVisitor.visitGraph(root, visitor))
                .map(TreeVisitor::getResult)
                .forEach(System.out::println);
    }
}
