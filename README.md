# alpro-k-kelompok-4
kode aplikasi shopping list furniture


import tkinter as tk
from tkinter import ttk, messagebox


funitures =  [
        {
            "namaBarang": "Meja",
            "deskripsi": "Terbuat dari Kayu Balok, Papan Kayu, Paku, Cat",
            "harga": 50000
        },
        {
            "namaBarang": "Kursi",
            "deskripsi": "Terbuat dari Kayu Balok, Papan Kayu, Paku, Cat",
            "harga": 25000
        },
        {
            "namaBarang": "Lemari",
            "deskripsi": "Terbuat dari Kayu Balok, Papan Kayu, Paku, Cat",
            "harga": 100000
        }
    ]
   


def showNamaBarang():
    funituresName = []
    for funiture in funitures:
        funituresName.append(funiture["namaBarang"])
    return funituresName


def submit():
    namaBarang = jenis_var.get()
    jumlahBarang = int(jumlah_var.get())
    for funiture in funitures:
        if (funiture["namaBarang"] == namaBarang ):
            label_namaBarang.config(text=funiture["namaBarang"])
            label_namaBarang.pack()
            label_deskripsi.config(text=funiture["deskripsi"])
            label_deskripsi.pack()
            label_harga.config(text=funiture["harga"]*jumlahBarang)
            label_harga.pack()


root = tk.Tk()
root.title("Jenis Harga Furniture")
root.geometry("300x200")  


jenis_var = tk.StringVar()
jenis_var.set("pilih barang")


jumlah_var = tk.StringVar()


jenis_label = tk.Label(root, text="Jenis Furniture:")
jenis_label.pack()


jenis_combobox = ttk.Combobox(root, textvariable=jenis_var, values=showNamaBarang())
jenis_combobox.pack()


jumlah_entry = tk.Label(root, text="Jumlah Furniture:")
jumlah_entry.pack()


jumlah_entry = ttk.Entry(root, textvariable=jumlah_var)
jumlah_entry.pack()


button_submit = ttk.Button(root, text="Submit", command=lambda: submit())
button_submit.pack()


label_namaBarang = tk.Label(root)
label_deskripsi = tk.Label(root)
label_harga = tk.Label(root)


root.mainloop()
