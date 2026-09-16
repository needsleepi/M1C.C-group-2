#include <iostream>
using namespace std;

class M1C {
private: 
    int spt;
    int a[200];
public:
    void nhap();
    void xuat();
    int timkiem(int x);
    void sapxep();
    void xoak(int k);   
    void chenk(int k); 
    void tach(int k, M1C &b, M1C &c);
    void gop(M1C b, M1C c);          
    int getSpt() { return spt; }
    int getElement(int i) { return a[i]; }
};

void M1C::nhap() {
    cout << "So phan tu: "; 
    cin >> spt;
    for (int i = 0; i < spt; i++) {
        cout << "a[" << i << "] = ";
        cin >> a[i];
    }
}

void M1C::xuat() {
    for (int i = 0; i < spt; i++)
        cout << a[i] << "\t";
    cout << endl;
}

int M1C::timkiem(int x) {
    int k = -1;
    for (int i = 0; i < spt; i++)
        if (a[i] == x)
            k = i;
    return k;
}

void M1C::sapxep() {
    for (int i = 0; i < spt - 1; i++) {
        for (int j = i + 1; j < spt; j++) {
            if (a[i] > a[j]) {
                int y = a[i];
                a[i] = a[j];
                a[j] = y;
           }
       }
   }
}

void M1C::xoak(int k) {
    if (k < 0 || k >= spt) {
        cout << "Vi tri xoa khong hop le!" << endl;
        return;
    }
    for (int i = k; i < spt - 1; i++) {
        a[i] = a[i + 1];
    }
    spt--;
}

void M1C::chenk(int k) {
    if (k < 0 || k > spt || spt >= 200) {
        cout << "Khong co vi tri hoac mang da day!" << endl;
        return;
    }
    cout << "Nhap gia tri can chen: ";
    int x;
    cin >> x;
    for (int i = spt; i > k; i--) {
        a[i] = a[i - 1];
    }
    a[k] = x;
    spt++;
}

void M1C::tach(int k, M1C &b, M1C &c) {
    if (k <= 0 || k >= spt) {
        cout << "Vi tri tach khong hop le!" << endl;
        return;
    }
    
    b.spt = k;
    for (int i = 0; i < k; i++) {
        b.a[i] = a[i];
    }
    
    c.spt = spt - k;
    for (int i = 0; i < c.spt; i++) {
        c.a[i] = a[k + i];
    }
}

void M1C::gop(M1C b, M1C c) {
    spt = b.spt + c.spt;
    int index = 0;
    
    for (int i = 0; i < b.spt; i++) {
        a[index++] = b.a[i];
    }
    
    for (int i = 0; i < c.spt; i++) {
        a[index++] = c.a[i];
    }
}

int main() {
    M1C x, y, z, kq_gop;
    x.nhap();
    cout << "\nMang ban dau:\n";
    x.xuat();
    
    int t;
    cout << "\nNhap phan tu can tim kiem: ";
    cin >> t;
    int vt = x.timkiem(t);
    
    if (vt == -1)
       cout << "Khong co phan tu " << t << " trong mang.\n";
    else
       cout << "Phan tu " << t << " nam o vi tri " << vt << "\n";
       
    cout << "\nMang sau khi sap xep tang dan:\n";
    x.sapxep();
    x.xuat();
    
    int h;
    cout << "\nNhap vi tri can xoa: ";
    cin >> h;
    x.xoak(h);
    cout << "Mang sau khi xoa:\n";
    x.xuat();
    
    int q; 
    cout << "\nNhap vi tri can chen: ";
    cin >> q;
    x.chenk(q);
    cout << "Mang sau khi chen la:\n";
    x.xuat();
    
    int k_tach;
    cout << "\nNhap chi so (index) de tach mang (tu 1 den " << x.getSpt() - 1 << "):\n";
    cout << "Nhap vi tri index de tach mang: ";
    cin >> k_tach;
    
    x.tach(k_tach, y, z);
    
    cout << "\nMang 1 sau khi tach:\n";
    y.xuat();
    
    cout << "Mang 2 sau khi tach:\n";
    z.xuat();
    
    kq_gop.gop(y, z);
    cout << "\nMang sau khi gop lai tu (y) va (z):\n";
    kq_gop.xuat();
    
    return 0;
}
