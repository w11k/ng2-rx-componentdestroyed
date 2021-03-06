
# Angular < 9 / ViewEngine

If you are using ...
 - Angular 8 or older
 - ViewEngine (instead of Ivy in Angular >= 9) 

... you have to use a previous version of this library. Please follow the instructions below.

## Installation

```
npm i --save @w11k/ngx-componentdestroyed@4.x.x
```

```
@Component({
  selector: 'foo',
  templateUrl: './foo.component.html'
})
export class FooComponent implements OnInit, OnDestroy {

  ngOnInit() {
    interval(1000)
        .pipe(
            untilComponentDestroyed(this)       // <--- 2. use the pipe operator
        )
        .subscribe();
  }

  ngOnDestroy() {                               // <--- 1. add empty stub 
  }
  
}
```

The TypeScript compiler will ensure that you implemented **1.** if you try to use **2.**.



