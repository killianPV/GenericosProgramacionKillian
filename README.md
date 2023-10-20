# GenericosProgramacionKillian

#EX_01

package EX_01;

public class App<T> {
    private Object[] array;
    private int size;

    public App() {
        array = new Object[10];  
        size = 0;
    }

    public boolean EstaVacío() {
        return size == 0;
    }

    public T removeFirst() {
        if (EstaVacío()) {
            return null;
        }

        @SuppressWarnings("unchecked")
        T firstElement = (T) array[0];
        System.arraycopy(array, 1, array, 0, size - 1);
        size--;
        return firstElement;
    }

    public T getFirst() {
        if (EstaVacío()) {
            return null;
        }

        @SuppressWarnings("unchecked")
        T firstElement = (T) array[0];
        return firstElement;
    }

    public void add(T element) {
        if (size == array.length) {
            Object[] newArray = new Object[array.length * 2];
            System.arraycopy(array, 0, newArray, 1, size);
            array = newArray;
        } else {
            System.arraycopy(array, 0, array, 1, size);
        }

        array[0] = element;
        size++;
    }

    @Override
    public String toString() {
        StringBuilder result = new StringBuilder("[");
        for (int i = 0; i < size; i++) {
            result.append(array[i]);
            if (i < size - 1) {
                result.append(", ");
            }
        }
        result.append("]");
        return result.toString();
    }


    public static void main(String[] args) {
        App<String> app = new App<>();
        
        System.out.println("Esta la App vacía? " + app.EstaVacío());
        
        app.add("Elemento 1");
        app.add("Elemento 2");
        app.add("Elemento 3");
        
        System.out.println("App: " + app);
        
        System.out.println("Borrando el primer elemento: " + app.removeFirst());
        
        System.out.println("La App después de borrar: " + app);
        
        System.out.println("Primer elemento: " + app.getFirst());
    }


}



#EX_02

package EX_02;

public class App<T> {
    private Object[] array;
    private int size;

    public App() {
        array = new Object[10]; 
        size = 0;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    public T removeFirst() {
        if (isEmpty()) {
            return null;
        }

        @SuppressWarnings("unchecked")
        T firstElement = (T) array[0];
        System.arraycopy(array, 1, array, 0, size - 1);
        size--;
        return firstElement;
    }

    public T getFirst() {
        if (isEmpty()) {
            return null;
        }

        @SuppressWarnings("unchecked")
        T firstElement = (T) array[0];
        return firstElement;
    }

    public void add(T element) {
        if (size == array.length) {
            Object[] newArray = new Object[array.length * 2];
            System.arraycopy(array, 0, newArray, 1, size);
            array = newArray;
        } else {
            System.arraycopy(array, 0, array, 1, size);
        }

        array[0] = element;
        size++;
    }

    @Override
    public String toString() {
        StringBuilder result = new StringBuilder("[");
        for (int i = 0; i < size; i++) {
            result.append(array[i]);
            if (i < size - 1) {
                result.append(", ");
            }
        }
        result.append("]");
        return result.toString();
    }

        public static void main(String[] args) {
            App<String> app = new App<>();
    
            System.out.println("Está la APP? " + app.isEmpty());
    
            app.add("Elemento 1");
            app.add("Elemento 2");
            app.add("Elemento 3");
    
            System.out.println("App: " + app);
    
            System.out.println("Borrando el primer elemento: " + app.removeFirst());
    
            System.out.println("La app después de borrar: " + app);
    
            System.out.println("Primer elemento: " + app.getFirst());
        }
    
}

