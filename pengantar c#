Jelajahi pemrograman berorientasi objek dengan kelas dan objek
Artikel
05/26/2022
9 menit untuk membaca
3 kontributor
Dalam tutorial ini, Anda akan membangun aplikasi konsol dan melihat fitur berorientasi objek dasar yang merupakan bagian dari bahasa C#.

Prasyarat
Kami merekomendasikanVisual Studiountuk Windows atau Mac. Anda dapat mengunduh versi gratis darihalaman unduhan Visual Studio. Visual Studio menyertakan .NET SDK.
Anda juga dapat menggunakan editorVisual Studio Code. Anda harus menginstal latest.NET SDKsecara terpisah.
Jika Anda lebih suka editor yang berbeda, Anda perlu menginstal SDK terbaru.NET.
Membuat aplikasi Anda
Menggunakan jendela terminal, buat direktori bernamakelas. Anda akan membangun aplikasi Anda di sana. Ubah ke direktori itu dan ketikkan jendela konsol. Perintah ini membuat aplikasi Anda. Buka Program.cs. Seharusnya terlihat seperti ini:dotnet new console

C #

Menyalin
// See https://aka.ms/new-console-template for more information
Console.WriteLine("Hello, World!");
Dalam tutorial ini, Anda akan membuat jenis baru yang mewakili rekening bank. Biasanya pengembang mendefinisikan setiap kelas dalam file teks yang berbeda. Itu membuatnya lebih mudah dikelola saat program bertambah besar. Buat file baru bernamaBankAccount.csdi direktoriClasses.

File ini akan berisi definisirekening bank. Pemrograman Berorientasi Objek mengatur kode dengan membuat jenis dalam bentukkelas. Kelas-kelas ini berisi kode yang mewakili entitas tertentu. Kelas mewakili rekening bank. Kode ini mengimplementasikan operasi tertentu melalui metode dan properti. Dalam tutorial ini, rekening bank mendukung perilaku ini:BankAccount

Ini memiliki nomor 10 digit yang secara unik mengidentifikasi rekening bank.
Ini memiliki string yang menyimpan nama atau nama pemilik.
Saldo dapat diambil.
Ini menerima setoran.
Ini menerima penarikan.
Saldo awal harus positif.
Penarikan tidak dapat menghasilkan saldo negatif.
Tentukan jenis rekening bank
Anda dapat mulai dengan membuat dasar-dasar kelas yang mendefinisikan perilaku itu. Buat file baru menggunakan perintahFile:New. Beri namaBankAccount.cs. Tambahkan kode berikut ke file.cs Rekening BankAnda:

C #

Menyalin
namespace Classes;

public class BankAccount
{
    public string Number { get; }
    public string Owner { get; set; }
    public decimal Balance { get; }

    public void MakeDeposit(decimal amount, DateTime date, string note)
    {
    }

    public void MakeWithdrawal(decimal amount, DateTime date, string note)
    {
    }
}
Sebelum melanjutkan, mari kita lihat apa yang telah Anda bangun. Thedeclaration menyediakan cara untuk mengatur kode Anda secara logis. Tutorial ini relatif kecil, jadi Anda akan meletakkan semua kode dalam satu namespace.namespace

public class BankAccountMenentukan kelas, atau jenis, yang Anda buat. Segala sesuatu di dalamandthat mengikuti deklarasi kelas mendefinisikan keadaan dan perilaku kelas. Ada limaanggotakelas. Tiga yang pertama adalahproperti. Properti adalah elemen data dan dapat memiliki kode yang memberlakukan validasi atau aturan lainnya. Dua yang terakhir adalahmetode. Metode adalah blok kode yang melakukan satu fungsi. Membaca nama masing-masing anggota hendaknya menyediakan informasi yang cukup bagi Anda atau pengembang lain untuk memahami apa yang kelas lakukan.{}BankAccount

Buka akun baru
Fitur pertama yang harus diterapkan adalah membuka rekening bank. Ketika pelanggan membuka akun, mereka harus memberikan saldo awal, dan informasi tentang pemilik atau pemilik akun tersebut.

Membuat objek baru dari tipe berarti mendefinisikankonstruktoryang menetapkan nilai-nilai tersebut. Konstruktoradalah anggota yang memiliki nama yang sama dengan kelas. Ini digunakan untuk menginisialisasi objek dari jenis kelas itu. Tambahkan konstruktor berikut ke thetype. Tempatkan kode berikut di atas deklarasi:BankAccountBankAccountMakeDeposit

C #

Menyalin
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
Kode sebelumnya mengidentifikasi properti objek yang sedang dibangun dengan memasukkanqualifier. Kualifikasi itu biasanya opsional dan dihilangkan. Anda juga bisa menulis:this

C #

Menyalin
public BankAccount(string name, decimal initialBalance)
{
    Owner = name;
    Balance = initialBalance;
}
Qualifier hanya diperlukan jika variabel atau parameter lokal memiliki nama yang sama dengan bidang atau properti tersebut. Kualifikasi dihilangkan di seluruh sisa artikel ini kecuali jika diperlukan.thisthis

Konstruktor dipanggil ketika Anda membuat objek menggunakanyang baru. Ganti Program linein.csdengan kode berikut (ganti dengan nama Anda):Console.WriteLine("Hello World!");<name>

C #

Menyalin
using Classes;

var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
Mari kita jalankan apa yang telah Anda bangun sejauh ini. Jika Anda menggunakan Visual Studio, PilihMulai tanpa debuggingdari menuDebug. Jika Anda menggunakan baris perintah, ketik direktori tempat Anda membuat proyek.dotnet run

Apakah Anda memperhatikan bahwa nomor rekening kosong? Sudah waktunya untuk memperbaikinya. Nomor akun harus ditetapkan ketika objek dibangun. Tapi seharusnya tidak menjadi tanggung jawab penelepon untuk membuatnya. Kode kelas harus tahu cara menetapkan nomor rekening baru. Cara sederhana adalah memulai dengan angka 10 digit. Tingkatkan saat setiap akun baru dibuat. Terakhir, simpan nomor akun saat ini ketika suatu objek dibangun.BankAccount

Tambahkan deklarasi anggota ke kelas. Tempatkan baris kode berikut setelah braceat pembuka di awal kelas:BankAccount{BankAccount

C #

Menyalin
private static int accountNumberSeed = 1234567890;
Theadalah anggota data. Ini, yang berarti hanya dapat diakses dengan kode di dalam kelas. Ini adalah cara untuk memisahkan tanggung jawab publik (seperti memiliki nomor akun) dari implementasi pribadi (bagaimana nomor akun dihasilkan). Itu juga, yang berarti dibagikan oleh semua orang. Nilai variabel non-statis unik untuk setiap instance dari theobject. Tambahkan dua baris berikut ke konstruktor untuk menetapkan nomor akun. Tempatkan mereka setelah baris yang mengatakan:accountNumberSeedprivateBankAccountstaticBankAccountBankAccountthis.Balance = initialBalance

C #

Menyalin
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
Ketikuntuk melihat hasilnya.dotnet run

Buat deposit dan penarikan
Kelas rekening bank Anda harus menerima setoran dan penarikan agar berfungsi dengan benar. Mari kita terapkan setoran dan penarikan dengan membuat jurnal setiap transaksi untuk akun. Melacak setiap transaksi memiliki beberapa keuntungan dibandingkan hanya memperbarui saldo pada setiap transaksi. Riwayat dapat digunakan untuk mengaudit semua transaksi dan mengelola saldo harian. Menghitung saldo dari riwayat semua transaksi bila diperlukan memastikan setiap kesalahan dalam satu transaksi yang diperbaiki akan tercermin dengan benar dalam saldo pada perhitungan berikutnya.

Mari kita mulai dengan membuat tipe baru untuk mewakili transaksi. Transaksi adalah jenis sederhana yang tidak memiliki tanggung jawab apa pun. Perlu beberapa properti. Buat file baru bernamaTransaction.cs. Tambahkan kode berikut ke dalamnya:

C #

Menyalin
namespace Classes;

public class Transaction
{
    public decimal Amount { get; }
    public DateTime Date { get; }
    public string Notes { get; }

    public Transaction(decimal amount, DateTime date, string note)
    {
        Amount = amount;
        Date = date;
        Notes = note;
    }
}
Sekarang, mari tambahkanList<T>ofobjects ke kelas. Tambahkan deklarasi berikut setelah konstruktor di fileBankAccount.csAnda:TransactionBankAccount

C #

Menyalin
private List<Transaction> allTransactions = new List<Transaction>();
Sekarang, mari kita hitung dengan benar. Saldo saat ini dapat ditemukan dengan menjumlahkan nilai semua transaksi. Karena kodenya saat ini, Anda hanya bisa mendapatkan saldo awal akun, jadi Anda harus memperbaruinya. Ganti barisBankAccount.csdengan kode berikut:BalanceBalancepublic decimal Balance { get; }

C #

Menyalin
public decimal Balance
{
    get
    {
        decimal balance = 0;
        foreach (var item in allTransactions)
        {
            balance += item.Amount;
        }

        return balance;
    }
}
Contoh ini menunjukkan aspek penting dariproperti. Anda sekarang menghitung saldo ketika programmer lain meminta nilainya. Perhitungan Anda menghitung semua transaksi, dan memberikan jumlah sebagai saldo saat ini.

Selanjutnya, terapkan theandmethods. Metode ini akan menegakkan dua aturan terakhir: saldo awal harus positif, dan penarikan apa pun tidak boleh membuat saldo negatif.MakeDepositMakeWithdrawal

Aturan-aturan ini memperkenalkan konseppengecualian. Cara standar untuk menunjukkan bahwa suatu metode tidak dapat menyelesaikan pekerjaannya dengan sukses adalah dengan memberikan pengecualian. Jenis pengecualian dan pesan yang terkait dengannya menggambarkan kesalahan. Di sini, metode ini memberikan pengecualian jika jumlah deposit tidak lebih besar dari 0. Themethod memberikan pengecualian jika jumlah penarikan tidak lebih besar dari 0, atau jika menerapkan penarikan menghasilkan saldo negatif. Tambahkan kode berikut setelah deklarasi daftar:MakeDepositMakeWithdrawalallTransactions

C #

Menyalin
public void MakeDeposit(decimal amount, DateTime date, string note)
{
    if (amount <= 0)
    {
        throw new ArgumentOutOfRangeException(nameof(amount), "Amount of deposit must be positive");
    }
    var deposit = new Transaction(amount, date, note);
    allTransactions.Add(deposit);
}

public void MakeWithdrawal(decimal amount, DateTime date, string note)
{
    if (amount <= 0)
    {
        throw new ArgumentOutOfRangeException(nameof(amount), "Amount of withdrawal must be positive");
    }
    if (Balance - amount < 0)
    {
        throw new InvalidOperationException("Not sufficient funds for this withdrawal");
    }
    var withdrawal = new Transaction(-amount, date, note);
    allTransactions.Add(withdrawal);
}
Pernyataanlemparanitu menimbulkanpengecualian. Eksekusi blok saat ini berakhir, dan transfer kontrol ke blok pencocokan pertama yang ditemukan di tumpukan panggilan. Anda akan menambahkan ablock untuk menguji kode ini nanti.catchcatch

Konstruktor harus mendapatkan satu perubahan sehingga menambahkan transaksi awal, daripada memperbarui saldo secara langsung. Karena Anda sudah menulisnya, sebut saja dari konstruktor Anda. Konstruktor yang sudah jadi akan terlihat seperti ini:MakeDeposit

C #

Menyalin
public BankAccount(string name, decimal initialBalance)
{
    Number = accountNumberSeed.ToString();
    accountNumberSeed++;

    Owner = name;
    MakeDeposit(initialBalance, DateTime.Now, "Initial balance");
}
DateTime.Nowadalah properti yang mengembalikan tanggal dan waktu saat ini. Uji kode ini dengan menambahkan beberapa setoran dan penarikan di metode Anda, mengikuti kode yang membuat yang baru:MainBankAccount

C #

Menyalin
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "Friend paid me back");
Console.WriteLine(account.Balance);
Selanjutnya, uji apakah Anda menangkap kondisi kesalahan dengan mencoba membuat akun dengan saldo negatif. Tambahkan kode berikut setelah kode sebelumnya yang baru saja Anda tambahkan:

C #

Menyalin
// Test that the initial balances must be positive.
BankAccount invalidAccount;
try
{
    invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
    return;
}
Anda menggunakanpernyataancobadantangkapuntuk menandai blok kode yang dapat menimbulkan pengecualian dan untuk menangkap kesalahan yang Anda harapkan. Anda dapat menggunakan teknik yang sama untuk menguji kode yang memberikan pengecualian untuk saldo negatif. Tambahkan kode berikut sebelum deklarasi yourmethod:invalidAccountMain

C #

Menyalin
// Test for a negative balance.
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
Simpan file dan ketikuntuk mencobanya.dotnet run

Tantangan - catat semua transaksi
Untuk menyelesaikan tutorial ini, Anda dapat menulis themethod yang membuat afor riwayat transaksi. Tambahkan metode ini ke thetype:GetAccountHistorystringBankAccount

C #

Menyalin
public string GetAccountHistory()
{
    var report = new System.Text.StringBuilder();

    decimal balance = 0;
    report.AppendLine("Date\t\tAmount\tBalance\tNote");
    foreach (var item in allTransactions)
    {
        balance += item.Amount;
        report.AppendLine($"{item.Date.ToShortDateString()}\t{item.Amount}\t{balance}\t{item.Notes}");
    }

    return report.ToString();
}
Riwayat menggunakan kelasStringBuilderuntuk memformat string yang berisi satu baris untuk setiap transaksi. Anda telah melihat kode pemformatan string sebelumnya dalam tutorial ini. Salah satu karakter baru adalah. Itu menyisipkan tab untuk memformat output.\t

Tambahkan baris ini untuk mengujinya diProgram.cs:

C #

Menyalin
Console.WriteLine(account.GetAccountHistory());
Jalankan program Anda untuk melihat hasilnya.
