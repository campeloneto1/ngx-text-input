# NgxTextInput

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 15.0.5.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## About

Form Input with label, validator and mask using Bootstrap Css and NGX Mask

## Getting started

Import Bootstrap CDN
```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js" integrity="sha384-w76AqPfDkMBDXo30jS1Sgez6pr3x5MlQ1ZAGC+nuZB+EYdgRZgiwxhTBTkF7CXvN" crossorigin="anonymous"></script>
```

Install de Ngx Text Input using NPM

```
npm install ngx-text-input
```

Import in your NgModel

```typescript
import { NgModule } from '@angular/core';
import { NgxTextInputModule } from './node_modules/ngx-text-input/src/lib/ngx-text-input.module';

@NgModule({
  imports: [
    NgxTextInputModule
  ],
})
export class MyModule {}

```

In your component ts, import FormGroup, FormBuilder and Validators, create a form and implement os NgOnInit your form:

```typescript
import { FormBuilder, FormGroup, Validators } from '@angular/forms';
export class AppComponent implements OnInit{
 form!: FormGroup

ngOnInit(): void {
    this.form = this.formBuilder.group({     
     text: [
        '',
        Validators.compose([
          Validators.required,
          Validators.minLength(4),
          Validators.maxLength(150),
        ]),
      ],    
      phone: [
        '',
        Validators.compose([
          Validators.required,
          Validators.minLength(11),
          Validators.maxLength(11),
        ]),
      ],
      number: [
        '',
        Validators.compose([
          Validators.required,
          Validators.min(0),
          Validators.max(100),
        ]),
      ],
      date: [
        '',
        Validators.compose([
          Validators.required,
        ]),
      ],
      time: [
        '',
        Validators.compose([
          Validators.required,
        ]),
      ],
      obs: [
        '',
        Validators.compose([
          Validators.required,
        ]),
      ],
    
    });
  }
}

```

Then, in your Component HTML file put this:

```html
<form [formGroup]="form" >
          <div class="row">
            <ngx-text-input class="col-sm-4" formControlName="text"  type="text" label="Text" id="text"  />
            <ngx-text-input class="col-sm-4" formControlName="email"  type="email" label="Email" id="email"  />
          </div>
          <div class="row">
            <ngx-text-input class="col-sm-4" formControlName="number"  type="number" label="Number" id="number"  />
            <ngx-text-input class="col-sm-4" formControlName="date"  type="date" label="Date" id="date"  />
            <ngx-text-input class="col-sm-4" formControlName="time"  type="time" label="Time" id="time"  />
          </div>
          <div class="row">
            <ngx-text-input class="col-sm-12" formControlName="obs"  type="textarea" label="Description" id="obs"  />
          </div>
      </form>
```
