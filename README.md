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

Part 1 solved with pattern-matching on the first 20 bit of bitstring that get returned by `:crypto.hash(:md5, "...")`, plus a bit of recursion. 2nd part solved the same way (though initial solution got extended to check more bits in the head of a hash).

### Day 5: Doesn't He Have Intern-Elves For This?

Both parts solved with `Regex`-es. Important to note that we rely on regex **back-references** to find pairs and repeatable groups. For example, `/(hello) \1/ =~ "hello hello"`; here `\1` refers to the first declared capture group `(hello)`.

### Day 6: Probably a Fire Hazard

Both parts solved with quite straightforward `Enum.reduce` and `Map.update(map, key, default, fun)` approach. Maybe not very performant (part 1 get calculated in 26-27 seconds, part 2 in 33-34 seconds), but works. We do not initialize light grid, because we leverage `default` argument of `Map.update/4` function. Input parsed with `Regex.run/2` and pattern matching on matched groups.
