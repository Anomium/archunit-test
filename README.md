# Archunit 🚀

ArchUnit es una biblioteca para probar la arquitectura del código de los proyectos Java utilizando simples pruebas unitarias.

En pocas palabras, archunit sirve para definir reglas para que se respete la arquitectura del proyecto.

En el siguiente codigo podemos ver un ejemplo:

```
  @Test
  public void nonDomainResidentInfrastructure() {
    JavaClasses javaClasses = new ClassFileImporter().importPackages("org.example.example.reporte.domain");
    
    noClasses()
        .that()
        .resideInAnyPackage("..infraestructure..")
        .should()
        .accessClassesThat()
        .resideInAPackage("..domain..")
        .check(javaClasses);
   
  }
```
**Ninguna clase que resida en el paquete de infraestructura debe acceder a clases que residan en el paquete de dominio.**
