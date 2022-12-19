<template>
  <div>
    <v-navigation-drawer absolute permanent left width="320">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Bumimedika </v-list-item-title>
          <v-list-item-subtitle> Admin PBF </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>
      <v-list>
        <v-list-group
          v-for="item in items"
          :key="item.title"
          :prepend-icon="item.action"
          no-action
        >
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </template>

          <v-list-item v-for="child in item.items" :key="child.title" link>
            <v-list-item-content>
              <v-list-item-title v-text="child.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>
<script>
export default {
  data: () => ({
    selectedItem: 1,
    items: [
      {
        action: 'mdi-database',
        items: [
          { title: 'Produk' },
          { title: 'Karyawan' },
          { title: 'Supplier' },
          { title: 'Pelanggan' },
          { title: 'Sales' },
          { title: 'Driver' }
        ],
        title: 'Master Data'
      },
      {
        action: 'mdi-cart',
        items: [
          { title: 'Penjualan' },
          { title: 'Pemesanan' },
          { title: 'Retur' },
          { title: 'Penerimaan Produk' },
          { title: 'Inkaso' },
          { title: 'Stok Opname' },
          { title: 'Tanda Terima Gudang' },
          { title: 'Tanda Terima Gudang' }
        ],
        title: 'Transaksi'
      },
      {
        action: 'mdi-file-chart',
        items: [
          { title: 'Arus Stok' },
          { title: 'Pemesanan' },
          { title: 'Penjualan' },
          { title: 'Statistika Obat' },
          { title: 'Penerimaan' },
          { title: 'Hutang' },
          { title: 'Inkaso' }
        ],
        title: 'Laporan'
      }
    ]
  })
}
</script>
