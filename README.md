# columns-mixin
Short, semantic mixin for quick columns with wrapping.

## Ever want a finite amount of columns in a wrapping grid with a static gutter?

```
.row {
  @include cols($cols: (1,1,1,1), $gutter: 1em, $column: #{'.card'});
}
```

## What about making those columns bump down to 2 on tablet and 1 on mobile?

```
.row {
  @media only screen and (max-width: 768px) {
    @include cols($cols: (1,1), $gutter: 1em, $column: #{'.card'});
  }
  @media only screen and (max-width: 500px) {
    @include cols$cols: (1), $gutter: 1em, $column: #{'.card'});
  }
}
```

## Just want to throw in a 3 column mixin and write some classes in the markup?

```
.row {
  @include cols();
}
```

```
<div class="row">
  <div class="col">Eat</div>
  <div class="col">at</div>
  <div class="col">Joe's</div>
</div>
```

## Either way, this is minimal, so you can focus on *important things*.

```
row {
  @include cols($cols: (1,1,1,1), $gutter: 1em, $column: #{'.card'});
  box-shadow: 10px 10px 0px 0px black;
  padding: 1em;

  @media only screen and (max-width: 500px) {
    @include cols($cols: (1), $gutter: 1em, $column: #{'.card'});
  }

  .header {
    flex-basis: 100%;
  }
  .card {
    background: yellow;
    box-shadow: 10px 10px 0px 0px black;
    color: black

    &:nth-child(2) {
      background: red;

      @media only screen and (max-width: 500px) {
        order: 1;
      }
    }
  }
}
```
