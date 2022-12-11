# Advent of Code 2015

Solutions written in Elixir as [Livebook](https://livebook.dev/) notebooks.

## Notes

### Day 1: Not Quite Lisp

Part 1 solved with `Enum.reduce/3` with pattern-matching. 2nd part solved with `Enum.reduce_while/3`, pattern-matching, and guards.

### Day 2: I Was Told There Would Be No Math

Part 1 solved with `Enum.reduce/3`, `Enum.min/1`, and simple arithmetics. 2nd part solved in a very similar way, just another set of calculations.

### Day 3: Perfectly Spherical Houses in a Vacuum

Part 1 solved `MapSet` and `Enum.reduce/3`; in the accumulator we store visited coordinates (houses) and current one, every step we update the current coordinate according too rules.

2nd part solved in a very similar way, but we just have to track coordinates of both Santa and Robo, and use two clauses in the reduce cycle; to simplify the code, we extracted new coordinate calculation to a module.

### Day 4: The Ideal Stocking Stuffer

Part 1 solved with pattern-matching on the first 20 bit of bitstring that get returned by `:crypto.hash(:md5, "...")`, plus a bit of recursion.
