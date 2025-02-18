import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Persona implements Comparable<Persona> {
    String nombre;
    int edad;

    public Persona(String nombre, int edad) { 
        this.nombre = nombre;
        this.edad = edad;
    }

    @Override
    public int compareTo(Persona otra) {
        return Integer.compare(this.edad, otra.edad);
    }

    @Override
    public String toString() {
        return nombre + " (" + edad + " años)";
    }
}

// 💡 La clase `TestComparable` debe estar fuera de `Persona`
public class TestComparable {
    public static void main(String[] args) {
        List<Persona> personas = new ArrayList<>();

        personas.add(new Persona("Ángel", 20));
        personas.add(new Persona("Sebastián", 25));
        personas.add(new Persona("Cano", 22));

        Collections.sort(personas); 

        System.out.println("Orden por edad:");
        for (Persona p : personas) {
            System.out.println(p);
        }
    }
}

