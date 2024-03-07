# JOBSHEET 03 MIGRATION, SEEDER, DB FAÇADE, QUERY BUILDER, dan ELOQUENT ORM

> Nama : Farid Fitriansah Alfarizi \
> NIM : 2241720055 \
> Absen : 12 \
> Kelas : 2F

## Pertanyaan

1. Pada Praktikum 1 - Tahap 5, apakah fungsi dari APP_KEY pada file setting .env Laravel?

    > APP_KEY pada file setting .env Laravel adalah kunci yang digunakan untuk enkripsi data dalam aplikasi. Ini penting untuk keamanan, terutama untuk sesi pengguna dan enkripsi data sensitif lainnya.

2. Pada Praktikum 1, bagaimana kita men-generate nilai untuk APP_KEY?

    > Menggunakan kode "php artisan key:generate"

3. Pada Praktikum 2.1 - Tahap 1, secara default Laravel memiliki berapa file migrasi? dan untuk apa saja file migrasi tersebut?

    > File migrasi terdiri dari 4 file:
    >
    > - 2021_08_19_000000_create_password_resets_tokens_table untuk membuat tabel password_resets_tokens untuk mengatur reset password token.
    > - 2021_08_19_000001_create_users_table untuk membuat tabel untuk data user.
    > - 2021_08_19_000002_create_failed_jobs_table: Menciptakan tabel failed_jobs untuk menyimpan data pekerjaan yang gagal pada aplikasi.
    > - 2021_08_19_000003_create_personal_access_tokens_table: Menciptakan tabel personal_access_tokens untuk menyimpan data token akses pribadi. Tabel ini digunakan untuk mengatur pengaturan seperti reset password token dan hal lainnya.

4. Secara default, file migrasi terdapat kode $table->timestamps();, apa tujuan/output dari fungsi tersebut?

    > Kode $table->timestamps(); menambahkan dua kolom created_at dan updated_at ke tabel yang sedang dimigrasikan. Ini digunakan untuk melacak waktu pembuatan dan pembaruan baris dalam tabel.

5. Pada File Migrasi, terdapat fungsi $table->id(); Tipe data apa yang dihasilkan dari fungsi tersebut?

    > Tipe data yang dihasilkan adalah BIGINT UNSIGNED

6. Apa bedanya hasil migrasi pada table m_level, antara menggunakan $table->id(); dengan menggunakan $table->id('level_id'); ?

    > Penggunaan $table->id(); dan $table->id('level_id'); dalam hasil migrasi pada tabel m_level sama-sama akan menghasilkan kolom id sebagai primary key. Perbedaannya hanya pada nama kolom yang dihasilkan.

7. Pada migration, Fungsi ->unique() digunakan untuk apa?

    > Fungsi ->unique() pada migration digunakan untuk menetapkan kolom dengan constraint unik, sehingga nilai di kolom tersebut harus unik dalam tabel.

8. Pada Praktikum 2.2 - Tahap 2, kenapa kolom level_id pada tabel m_user menggunakan $tabel->unsignedBigInteger('level_id'), sedangkan kolom level_id pada tabel m_level menggunakan $tabel->id('level_id') ?

    > Penggunaan $table->unsignedBigInteger('level_id') pada tabel m_user digunakan karena kolom level_id dianggap sebagai foreign key ke tabel m_level, sementara pada tabel m_level penggunaan $table->id('level_id') digunakan karena level_id adalah primary key di tabel tersebut.

9. Pada Praktikum 3 - Tahap 6, apa tujuan dari Class Hash? dan apa maksud dari kode program Hash::make('1234');?

    > Tujuan dari Class Hash adalah untuk melakukan hashing password atau data sensitif lainnya dalam aplikasi. Kode program Hash::make('1234') menghasilkan string hash untuk string '1234', yang digunakan untuk penyimpanan yang aman di database.

10. Pada Praktikum 4 - Tahap 3/5/7, pada query builder terdapat tanda tanya (?), apa kegunaan dari tanda tanya (?) tersebut?

    > Tanda tanya (?) pada query builder digunakan untuk menandai placeholder parameter. Nilai-nilai untuk parameter-parameter ini akan diikat ke placeholder ini secara aman untuk mencegah serangan SQL injection.

11. Pada Praktikum 6 - Tahap 3, apa tujuan penulisan kode protected $table = ‘m_user’; dan protected $primaryKey = ‘user_id’; ?

    > Penulisan kode protected $table = ‘m_user’; dan protected $primaryKey = ‘user_id’; digunakan untuk menentukan tabel dan primary key yang terkait dengan model m_user. Ini membantu Eloquent ORM dalam mengenali tabel mana yang harus diakses dan primary key mana yang harus digunakan.

12. Menurut kalian, lebih mudah menggunakan mana dalam melakukan operasi CRUD ke database (DB Façade / Query Builder / Eloquent ORM) ? jelaskan

    > Eloquent ORM lebih mudah digunakan karena menyediakan antarmuka yang lebih dekat dengan objek daripada query builder atau DB Façade. Eloquent ORM juga menyediakan banyak fitur bawaan untuk mempermudah pengembangan aplikasi, seperti relasi antar-tabel yang mudah digunakan.
