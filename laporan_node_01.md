```java
import java.util.Scanner;
public class node_01{
    Quiz2 head;
    int size;
    public class Quiz2 {
    Quiz2 head;
    int size;
    int nomor;
    String nama;
    Quiz2 prev, next;
    public String nomorHp;
    Quiz2(Quiz2 prev, int nomor, String nama, int nomerHp, Quiz2 next){
    this.prev = prev;
    this.nomor = nomor;
    this.nama = nama;
    this.next = next;
    }
}
    public void node_01(){
        head = null;
        size = 1;
    }
    public boolean isEmpty(){
        return head == null;
    }
    public void addLast(int nomor, String nama, int nomorHp){           
        if (isEmpty()){
            head  = new Quiz2(null, nomor, nama, nomorHp, null);
        }else{
            Quiz2 current = head;
        while (current.next != null){
                current = current.next;
            }
        Quiz2 newNode = new Quiz2(current, nomor, nama, nomorHp, null);
            current.next = newNode;
            size++;
        }
    }
    public void removeFirst() throws Exception{
        if(isEmpty()){
            throw new Exception("Linked List Masih kosong, tidak dapat dihapus!");
        }else if (size == 1){
            removeLast();
        }else{
            System.out.println(head.nama+"Sudah Divaksin");
            head = head.next;
            head.prev = null;
            size--;
        }
    }
    public void removeLast() throws Exception {
        if(isEmpty()){
            throw new Exception("Linked list masih kosong, tidak dapat dihapus!");
        }else if (head.next == null){
            System.out.println(head.nama+"Sudah Divaksin");
            head = null;
            size--;
            return;
        }
        Quiz2 current = head;
        while (current.next.next != null){
            current = current.next;
        }
        current.next = null;
        size--;
    }
    public void print(){
        System.out.println("-------------------------------------");
        System.out.println("  DAFTAR ANTRIAN RESTO IBU KANDUANG   ");
        System.out.println("-------------------------------------"); 
        System.out.println("| No\t| Nama Customer"+"\t\t| No Hp");
        if(!isEmpty()){
            Quiz2 tmp = head;
            while (tmp != null){
                System.out.print("| "+tmp.nomor+"\t| "+tmp.nama+" "+"\t\t| "+tmp.nomorHp+" \n");
                tmp = tmp.next;
            }
            System.out.println("\nTotal Antrian "+size);
        }else{
            System.out.println("Linked List Kosong");
        }
    }
class node_01Main {
    public static void menu(){
        System.out.println("Menu");
        System.out.println(" 1. Tambah Antrian\n 2. Cetak Antrian\n 3. Hapus Antrian\n 4. Laporan pengurutan pesanan by nama\n 5. Hitung total pendapatan\n 6. Keluar\n");
    }
    public static void main (String[] args) throws Exception{
        System.out.println("======= Quiz 2 PRAKTIKUM ASD TI - 1G dan TI - 1F =======");
        System.out.println("dibuat oleh : Abdullah Azzam");
        System.out.println("NIM         : 2141720073");
        System.out.println("Absen       : 01");
        System.out.println("========================================================");
        Scanner a = new Scanner(System.in);
        Scanner b = new Scanner(System.in);
        Scanner c = new Scanner(System.in);
        node_01 dll = new node_01();
            int pilih;
            do{
                menu();
                System.out.print("Pilih(1-5) : ");
                pilih = a.nextInt();
                a.nextLine();
                switch(pilih){
                    case 1:
                    System.out.println("-----------------------------------");
                    System.out.println("Masukkan Data Pembeli");
                    System.out.println("-----------------------------------");
                    System.out.print("Nomor Antrian\t: ");
                    int nomor = a.nextInt();
                    System.out.print("Nama Customer\t: ");
                    String nama = b.nextLine();
                    System.out.print("Nomor Hp\t:");
                    int nomorHp = c.nextInt();
                    dll.addLast(nomor, nama, nomorHp);
                    b.nextLine();
                    break;
                    case 2:
                    dll.print();
                    break;
                    case 3:
                    dll.removeFirst();
                    dll.print();
                    break;
                    case 4:
                    break;
                    case 5:
                    break;
                    case 6:
                    System.exit(0);
                    break;
                } 
            }while (pilih == 1 || pilih == 2 || pilih == 3 || pilih == 4 || pilih ==5 || pilih ==6);
    }
}
}
```
<img src="hasil.PNG">
<img src="hasil2.PNG">