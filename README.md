Nombre: Daniel Felipe Sainea Corredor
Código: 55823010

Taller consultas Angular

Componentes básicos


Qué es un componente y su estructura (decorador @Component, selector, template, style).

Según la página angular en “Introduction to components and templates”: Un componente controla una parte de la pantalla llamada vista .  
En Angular, el decorador es útil para identificar la clase inmediatamente inferior como una clase de componente y especifica sus metadatos.
@Component()
En la página Component Decorator se señala que es un decorador que designa una clase TypeScript como un componente Stencil. Cada componente Stencil se transforma en un componente web durante la compilación.
selector
Según la página “Angular”, este decorador es un selector CSS que le indica a Angular que genere e inserte una instancia de este componente en el lugar donde se encuentre la etiqueta correspondiente dentro del HTML de la plantilla. Por ejemplo, si el HTML de una aplicación incluye <app-hero-list></app-hero-list>, Angular coloca una instancia de HeroListComponent entre esas etiquetas.
template
Como indica la página “Angular”, la ruta relativa de la plantilla HTML de este componente. Como alternativa, se puede proporcionar la plantilla HTML directamente en línea como valor de la propiedad. Esta plantilla define la vista hosttemplate del componente.
style
Esta propiedad se utiliza para definir los estilos específicos para el componente en lugar de depender de una hoja de estilos global.


Diferencia entre un componente de página (vista completa) y uno reutilizable (ej. ProductCard).
Como señala la página “Angular”, la mayor diferencia se encuentra en que: Los componentes independientes ofrecen una forma simplificada de crear aplicaciones Angular. Es decir podremos reutilizar este componente varias veces en nuestra página, y facilitando el orden del código, y que si un error afecta ese componente, no falle la página completa.
Standalone Components (Angular 15+)


Qué significa que no hay módulos (NgModule).
Los Standalone Components permiten crear componentes sin necesidad de un NgModule, simplificando la estructura de la aplicación.
Uso de la propiedad standalone: true.
Define un componente como independiente, sin necesidad de estar en un NgModule.
Ejemplo:
@Component({
  selector: 'app-mi-componente',
  standalone: true,
})
export class MiComponenteComponent {}



Importación de otros componentes/módulos dentro de imports.

Se puede importar otros componentes o módulos dentro de la propiedad imports de un Standalone Component.
Ejemplo:
@Component({
  selector: 'app-mi-componente',
  standalone: true,
  imports: [OtroComponente]
})
export class MiComponenteComponent {}



Data Binding


Interpolación ({{ }})
Permite mostrar valores dinámicos en la vista.
<h1>{{ titulo }}</h1>

Property Binding ([prop]="value") 
Enlaza propiedades del HTML a valores del componente.
<input [value]="nombre">

Event Binding ((event)="handler()") 
Asocia eventos (como clics) a métodos del componente.
<button (click)="onClick()">Haz clic</button>


Directivas estructurales


*ngFor 
Itera sobre una colección para generar elementos.
<ul>
  <li *ngFor="let item of items">{{ item }}</li>
</ul>

*ngIf.
Muestra u oculta elementos según una condición.
<div *ngIf="mostrarElemento">Visible si 'mostrarElemento' es true</div>

Decoradores @Input y @Output


@Input()
Permite pasar datos de un componente padre a un hijo.
@Input() mensaje: string = '';

@Output()
Emite eventos desde un componente hijo a un componente padre.
@Output() mensajeEmitido = new EventEmitter<string>();


Referencias: 
Angular. (s. f.). https://v17.angular.io/guide/architecture-components
Component Decorator | Stencil. (s. f.). https://stenciljs.com/docs/component
Angular. (s. f.-b). https://v17.angular.io/guide/standalone-components
Angular. (2023). Standalone Components in Angular. Recuperado de https://angular.io


Angular. (2023). Data binding and interpolation. Recuperado de https://angular.io/guide/template-syntax

