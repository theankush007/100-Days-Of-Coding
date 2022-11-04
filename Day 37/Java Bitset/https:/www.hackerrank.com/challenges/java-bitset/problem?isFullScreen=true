import java.util.BitSet;
import java.util.Scanner;
import java.util.stream.Collectors;
import java.util.stream.IntStream;
import java.util.stream.Stream;

enum Operation {
    OR("OR"),
    XOR("XOR"),
    AND("AND"),
    SET("SET"),
    FLIP("FLIP");

    final String name;

    Operation(String name) {
        this.name = name;
    }
}

public class Solution {

    public static void main(String[] args) {
        final var scanner = new Scanner(System.in);

        final var firstLine = Stream.of(scanner.nextLine().split(" "))
            .mapToInt(Integer::parseInt)
            .toArray();
        final var n = firstLine[0];
        final var m = firstLine[1];
        final var bitsets = new BitSet[]{new BitSet(n), new BitSet(n)};

        final var output = IntStream.range(0, m)
            .mapToObj(i -> {
                final var input = scanner.nextLine().split(" ");
                final int i1 = Integer.parseInt(input[1]) - 1;
                final int i2 = Integer.parseInt(input[2]);
                switch (Operation.valueOf(input[0])) {
                    case OR -> bitsets[i1].or(bitsets[i2 - 1]);
                    case XOR -> bitsets[i1].xor(bitsets[i2 - 1]);
                    case AND -> bitsets[i1].and(bitsets[i2 - 1]);
                    case SET -> bitsets[i1].set(i2);
                    case FLIP -> bitsets[i1].flip(i2);
                }
                return String.format("%s %s", bitsets[0].cardinality(), bitsets[1].cardinality());
            })
            .collect(Collectors.joining("\n"));

        System.out.println(output);
    }
}
