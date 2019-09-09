
#include <iostream>
#include <string>

using namespace std;
void input();
void tambah();
void lihat();
void cari();
void hapus();

char kembali;
int pilih, jml2;
int jml =  0; // jumlah data
bool chek_input = false; // variabel helper
bool chek_tampil = false; // variabel helper

struct input{
    char nama[30],
		 tempat[20],
		 jk[20],
		 agama[10],
		 status[10],
		 pekerjaan[20],
		 kw[10],
		 provinsi[30],
		 kota[20],
		 rt[10],
		 kel[20],
		 kec[20],
		 alamat[30],
		 nik[20],
		 tgl[10],
		 gol[2];

}data[99];


int main(){
        do{
            cout<<"----Menu----";
            cout<<"\n 1. Input Data ";
            cout<<"\n 2. Tambah Data ";
            cout<<"\n 3. Lihat Data ";
            cout<<"\n 4. Cari Data ";
            cout<<"\n 5. Hapus Data ";
            cout<<"\nPilih : "; cin>>pilih;

            switch(pilih){
                case 1:
					input();
                break;
               case 2:
					tambah();
               break;
                case 3:
					lihat();
                break;
                case 4:
					cari();
                break;
                case 5:
					hapus();
                break;
                default:
                    cout<<"Pilihan Salah"<<endl;
                break;
            }
            cout<<"Kembali ke Menu? (Y?N)";cin>>kembali;
        }while(kembali=='Y'||kembali=='y');
    }

void hapus(){
	
	cout << "Hapus Data : " << endl;
	
	// chek tampil apakah udah diinputkan sebelumnya atau tidak
	if (chek_tampil == false)
	{
		cout << "Data input Kosong" << endl;
	}
	else{
		int hapus = 0;
		for (int i = 0; i < jml; i++)
		{
			cout << "data ke-" << i+1 << endl;
			cout << "NIK : " << data[i].nik << endl;
			cout << "Nama : " << data[i].nama << endl;
			cout << endl;
		}
		cout << "Hapus Data ke- : ";
		cin >> hapus;
		
		int chek_hapus = hapus - 1; //  var helper
		bool ket_hapus = true;
		if (hapus > jml)
		{
			cout << "data ke-"<<hapus << " tidak ada" <<endl;
			ket_hapus = false;
			
		}
		else{
		if ((chek_hapus > 0) || ( (jml-1) > 0) ) // jika jumlah datanya lebih dari 1
		{
			for (int x = hapus-1; x < jml-1; x++)
			{
				data[x].provinsi = data[x+1].provinsi;
				data[x].nik = data[x+1].nik;
				data[x].nama = data[x+1].nama;
				data[x].tempat  = data[x+1].tempat;
				data[x].tgl = data[x+1].tgl;
				data[x].jk = data[x+1].jk;
				data[x].gol = data[x+1].gol;
				data[x].alamat = data[x+1].alamat;
				data[x].rt = data[x+1].rt;
				data[x].kel = data[x+1].kel;
				data[x].kec = data[x+1].kec;
				data[x].agama = data[x+1].agama;
				data[x].status = data[x+1].status;
				data[x].pekerjaan = data[x+1].pekerjaan;
				data[x].kw = data[x+1].kw;
			}	
		}
		else{  // jika jumlah datanya 1
			chek_input = false;
			chek_tampil = false;
			for (int x = hapus; x <= jml-1; x++)
			{
				data[x].provinsi = data[x+1].provinsi;
				data[x].nik = data[x+1].nik;
				data[x].nama = data[x+1].nama;
				data[x].tempat  = data[x+1].tempat;
				data[x].tgl = data[x+1].tgl;
				data[x].jk = data[x+1].jk;
				data[x].gol = data[x+1].gol;
				data[x].alamat = data[x+1].alamat;
				data[x].rt = data[x+1].rt;
				data[x].kel = data[x+1].kel;
				data[x].kec = data[x+1].kec;
				data[x].agama = data[x+1].agama;
				data[x].status = data[x+1].status;
				data[x].pekerjaan = data[x+1].pekerjaan;
				data[x].kw = data[x+1].kw;
			}
		
	}
}
	
	
	if (ket_hapus)
	{
		jml = jml - 1;
		cout << endl;
		cout << "Data Berhasil Dihapus " << endl;
	}
	

	
	
}
}

void cari(){
	 // chek tampil apakah udah diinputkan sebelumnya atau tidak 
	 if (chek_tampil == false) { 
		 cout << "Data input Kosong" << endl; }
	  else{
		string cari;
		
		cout << "Cari Data " << endl;
		cout << "Masukkan NIK :  "; // pencarian berdasarkan NIK
		cin >> cari;
	
	int chek_cari = 0; // variabel helper
	
	for (int x = 0; x < jml; x++)
	{
		if (cari == data[x].nik)
		{
			chek_cari++; // jika ditemukkan bertambah 1
			
			cout << "Data Ke-" <<x+1 << endl;
			cout << "-----------------------------------------------" << endl;
			cout<<"Provinsi: " << data[x].provinsi << endl;
			cout<<"NIK: " << data[x].nik << endl;
			cout<<"Nama: " << data[x].nama << endl;
			cout<<"Tempat Lahir: " << data[x].tempat << endl; 
			cout<<"Tanggal Lahir: " << data[x].tgl << endl;
			cout<<"Jenis Kelamin: " << data[x].jk << endl;;
			cout<<"Gol.darah: " << data[x].gol << endl;;
			cout<<"Alamat: " << data[x].alamat << endl;
			cout<<"RT/RW: " << data[x].rt << endl;
			cout<<"Kel/Desa: " << data[x].kel << endl;
			cout<<"Kecamatan: " << data[x].kec << endl;
			cout<<"Agama: " << data[x].agama << endl;
			cout<<"Status Perkawinan: " << data[x].status << endl;
			cout <<"Pekerjaan: " << data[x].pekerjaan << endl;
			cout<<"Kewarganegaraan: " << data[x].kw << endl;
			cout<<"Berlaku Hingga: SEUMUR HIDUP";
			
			cout << endl << endl << endl;	
		}
		
	}
	
	// jika tidak ditemukkan 
	if(chek_cari == 0){
		cout << "Data Tidak Ditemukan " << endl << endl;
	}
}
}

void input(){
	// chek input apakah udah diinputkan sebelumnya atau tidak
	if (chek_input == true)
	{
		cout << "Data Udah Di input " << endl;
	}
	else{
		chek_input = true;
		chek_tampil = true;
		cout << "INput Data : " << endl;
		cout << endl;
		cout<<"Inputkan berapa data= ";
		cin>>jml;
		for(int x=0;x<jml;x++)
		{	
			
			cout<<"Data ke-"<<x+1<<endl;
			
			cin.ignore();
			cout<<"Provinsi: ";
			cin.getline(data[x].provinsi, sizeof(data[x].provinsi));
			
			cout<<"NIK: ";
			cin>>data[x].nik;
			
		

			cin.ignore();
			cout<<"Nama: ";
			cin.getline(data[x].nama, sizeof(data[x].nama));

			cout<<"Tempat Lahir: ";
			cin.getline(data[x].tempat, sizeof(data[x].tempat));
			
			cout<<"Tanggal Lahir: ";
			cin>>data[x].tgl;
		   
			cout<<"Jenis Kelamin: ";
			cin>>data[x].jk;

			cout<<"Gol.darah: ";
			cin>>data[x].gol;

			cin.ignore();
			cout<<"Alamat: ";
			cin.getline(data[x].alamat,30);

			cout<<"RT/RW: ";
			cin>>data[x].rt;
			 
			cin.ignore();
			cout<<"Kel/Desa: ";
			cin.getline(data[x].kel,sizeof(data[x]));

			cout<<"Kecamatan: ";
			cin.getline(data[x].kec,sizeof(data[x]));

			cout<<"Agama: ";
			cin>>data[x].agama;
			
			cin.ignore();
			cout<<"Status Perkawinan: ";
			cin>>data[x].status;
			
			cin.ignore();
			cout <<"Pekerjaan: ";
			cin>>data[x].pekerjaan;
			
			cin.ignore();
			cout<<"Kewarganegaraan: ";
			cin>>data[x].kw;
			
			cout<<"Berlaku Hingga: SEUMUR HIDUP" << endl << endl;
		}
	}

}

void tambah(){
	// chek tampil apakah udah diinputkan sebelumnya atau tidak
	if (chek_tampil == false)
	{
		cout << "Data input Kosong " << endl;
	}
	else{
		cout << "Tambah Data : " << endl;
		jml++;
		cin.ignore();
        cout<<"Provinsi: ";
        cin.getline(data[jml-1].provinsi, sizeof(data[jml-1].provinsi));

        cout<<"NIK: ";
        cin>>data[jml-1].nik;

        cin.ignore();
		cout<<"Nama: ";
		cin.getline(data[jml-1].nama, sizeof(data[jml-1].nama));

		cout<<"Tempat Lahir: ";
		cin.getline(data[jml-1].tempat, sizeof(data[jml-1].tempat));
        
		cout<<"Tanggal Lahir: ";
        cin>>data[jml-1].tgl;
        
		cout<<"Jenis Kelamin: ";
        cin>>data[jml-1].jk;

		cout<<"Gol.darah: ";
		cin>>data[jml-1].gol;

		cin.ignore();
		cout<<"Alamat: ";
		cin.getline(data[jml-1].alamat,30);

		
        cout<<"RT/RW: ";
        cin>>data[jml-1].rt;
        

		cin.ignore();
        cout<<"Kel/Desa: ";
        cin.getline(data[jml-1].kel,sizeof(data[jml-1]));

		cout<<"Kecamatan: ";
		cin.getline(data[jml-1].kec,sizeof(data[jml-1]));

        cout<<"Agama: ";
        cin>>data[jml-1].agama;
        
        cin.ignore();
        cout<<"Status Perkawinan: ";
        cin>>data[jml-1].status;
        
        cin.ignore();
        cout <<"Pekerjaan: ";
        cin>>data[jml-1].pekerjaan;
        
        cin.ignore();
        cout<<"Kewarganegaraan: ";
        cin>>data[jml-1].kw;
        
        cin.ignore();
        cout<<"Berlaku Hingga: SEUMUR HIDUP";
        
        cout << endl <<endl;
        cout <<"berhasil ";
	}
}
void lihat(){
	
	// chek tampil apakah udah diinputkan sebelumnya atau tidak
	if (chek_tampil == false)
	{
		cout << "Data Input Kosong" << endl;
		
	}
	else{
		cout << "Lihat Data :" << endl;
		for(int x=0;x<jml;x++)
		{
			cout << "Data Ke-" <<x+1 << endl;
			cout << "-----------------------------------------------" << endl;
			cout<<"Provinsi: " << data[x].provinsi << endl;
			cout<<"NIK: " << data[x].nik << endl;
			cout<<"Nama: " << data[x].nama << endl;
			cout<<"Tempat Lahir: " << data[x].tempat << endl; 
			cout<<"Tanggal Lahir: " << data[x].tgl << endl;
			cout<<"Jenis Kelamin: " << data[x].jk << endl;;
			cout<<"Gol.darah: " << data[x].gol << endl;;
			cout<<"Alamat: " << data[x].alamat << endl;
			cout<<"RT/RW: " << data[x].rt << endl;
			cout<<"Kel/Desa: " << data[x].kel << endl;
			cout<<"Kecamatan: " << data[x].kec << endl;
			cout<<"Agama: " << data[x].agama << endl;
			cout<<"Status Perkawinan: " << data[x].status << endl;
			cout <<"Pekerjaan: " << data[x].pekerjaan << endl;
			cout<<"Kewarganegaraan: " << data[x].kw << endl;
			cout<<"Berlaku Hingga: SEUMUR HIDUP";
			
			cout << endl << endl;
		}
		
	}
	
}
