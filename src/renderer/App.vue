<template>
  <div id="app">
    <top-left-nav v-if="$route.name !== 'Home'"></top-left-nav>

    <div class="container-fluid">
      <router-view></router-view>
    </div>

      <loading-modal></loading-modal>
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.min.css'
  import 'bootstrap/dist/js/bootstrap.min.js'
  import TopLeftNav from "./components/TopLeftNav"
  import LoadingModal from './components/Modals/Loading'

  export default {
    name: 'ont-wallet-test',
    components: {TopLeftNav, LoadingModal},
    watch: {
      '$route': 'hideLoadingPage'
    },
    created() {
      
    },
    methods: {
      hideLoadingPage() {
        this.$store.dispatch('hideLoadingModals')
      }
    }
  }
</script>

<style>
  /* CSS */
  @font-face {
    font-family: SourceSansPro;
    src: url('../../static/fonts/SourceSansPro-Semibold.ttf');
  }

  @font-face {
    font-family: AvenirNext-Bold;
    src: url('../../static/fonts/AvenirNextBold.ttf');
  }
  @font-face {
    font-family: AvenirNext-Medium;
    src: url('../../static/fonts/AvenirNextMedium.ttf');
  }
  @font-face {
    font-family: AvenirNext-Regular;
    src: url('../../static/fonts/avenirnextregular.otf');
  }

  .loading {
    text-align: center;
    background: rgba(0, 0, 0, 0.05);
    width: 100%;
    height: 100%;
  }

  .container-fluid {
    padding-left: 5.13rem !important;
  }

  .font-regular {
    font-family: 'AvenirNext-Regular';
    color: #000000;
    font-size: 0.88rem;
  }

  .font-medium {
    font-family: 'AvenirNext-Medium';
    color: #5E6369;
    font-size: 0.88rem;
  }

  .font-medium-black {
    font-family: 'AvenirNext-Medium';
    color: #000000;
    font-size: 0.88rem;
  }

  .font-bold {
    font-family: 'AvenirNext-Bold';
    color: #5E6369;
    font-size: 14px;
  }


  /* Button CSS */
  .btn-container {
    width: 540px;
    margin: 25px auto;
  }

  .btn-next,
  .btn-cancel {
    min-width: 6.25rem !important;
    height: 2.13rem !important;
    font-family: AvenirNext-Medium !important;
    font-size: 14px !important;
    text-align: center !important;
  }

  .btn-cancel {
    background: #F5F7FB !important;
    border-radius: 0 !important;
    color: #5E6369 !important;
    border: none !important;
  }

  .btn-next {
    background: #196BD8 !important;
    color: #ffffff !important;
    border-radius: 0 !important;
    border: none !important;
  }

  .btn-add {
    width: 80px !important;
    height: 34px !important;
    background: #FBE45A !important;
    border-radius: 0 !important;
    font-family: 'AvenirNext-Bold' !important;
    border: none !important;
    font-size: 18px !important;
  }

  .btn-add:hover {
    border: 1px solid #FBE45A !important;
  }

  .btn-cancel span, .btn-next span {
    width: 100%;
  }

  .input {
    border-radius: 0 !important;
    background: #FFFFFF !important;
    border: 1px solid #DFE2E9 !important;
    height: 34px !important;
  }

  .error-input {
    border-color:red !important;
  }

  .footer-btns {
    position: fixed;
    bottom: 0;
    width: calc(100% - 4rem);
    height: 85px;
    left: 4rem;
    background: #FFFFFF;
    box-shadow: 0 -1px 6px 0 #F2F2F2;
    z-index: 1000;
  }

  .footer-btn-container {
    width: 540px;
    margin: 20px auto;
  }

  .footer-btn-container :last-child {
    float: right;
  }

  .ant-spin-text {
    color: white !important;
    text-shadow: none !important;
  }

  /* .ant-spin-dot i {
    background-color: white !important;
  } */

  .v-validate-span-errors {
    color: red;
    font-size: 12px;
  }

  .refresh-icon {
    display: inline-block;
    cursor: pointer;
    font-size: 18px;
    color:#196BD8;
  }
  .refresh-icon:hover{
    color: rgba(25, 130, 216, 0.658);
  }
  .add-icon {
    background-image: url('./assets/add.png');
    display:inline-block;
    width: 18px;
    height:18px;
    background-size: cover;
    cursor: pointer;
  }
  .add-icon:hover {
    background-image: url('./assets/add-hover.png');
  }
  .asset-container {
    height:40vh;
    overflow:auto;
  }

.asset-container::-webkit-scrollbar {
    -webkit-appearance: none;
}

.asset-container::-webkit-scrollbar:vertical {
    width: 10px;
    height:15px;
}

.asset-container::-webkit-scrollbar-thumb {
    border-radius: 4px;
    border: 2px solid white; /* should match background, can't be transparent */
    background-color:#dddddd;
}

 .wallet-balance {
    font-size: 16px;
    color: #000000;
    font-family: 'AvenirNext-Bold';
    position: relative;
    margin-top: 30px;
    display:flex;
    justify-content: space-between;
    padding-bottom: 5px;
    padding-right:10px;
    border-bottom:1px solid #DFE2E9;
  }

  .wallet-balance :first-child {
    float: left;
    margin-right: 20px;
  }


  .asset-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 10px;
    /* padding-right:20px; */
    width:100%;
  }

  .asset-ong {
    height: 2.56rem;
    line-height: 2.56rem;
    margin-top: 12px;
  }

  .asset-label {
    font-family: AvenirNext-Medium;
    font-size: 0.88rem;
    color: #515457;
    float: left;
    margin-right: 12px;
  }

  .asset-amount {
    font-family: AvenirNext-Medium;
    font-size: 18px;
    color: #000000;
  }

  .asset-value {
    padding-left: 3rem;
    font-family: AvenirNext-Medium;
    font-size: 14px;
    color: #000000;
    margin-bottom: 20px;
  }

  .asset-btn {
    border-radius: 0;
    background: #196BD8;
    font-family: AvenirNext-Medium;
    font-size: 14px;
    color: #FFFFFF;
    margin-right: 40px;
    margin-bottom: 60px;
    border: none;
    width:120px;
    height: 34px;
  }

  .claim-ong-container {
    display:flex;
    justify-content: space-between;
    align-items: flex-end;
    padding-bottom:10px;
    border-bottom: 1px solid #dddddd;
    margin-bottom:20px;
  }

  .claim-ong-item {
    margin-bottom: 10px;
    position: relative;
  }

  .claim-ong-item :first-child {
    font-family: AvenirNext-Medium;
    font-size: 12px;
    color: #515457;
    margin-right: 8px;
    width: 100px;
    display: block;
    float: left;
  }

  .claim-ong-item :nth-child(2) {
    font-family: AvenirNext-Medium;
    font-size: 12px;
    color: #000000;
    float: left;
  }
  .redeem-container {
    display: flex;
    align-items: center;
  }

  .btn-redeem {
    border: none;
    color: #227EEC;
    font-size: 14px;
    font-family: AvenirNext-Medium;
    font-weight: 500;
    padding-right: 0;
  }
  .btn-redeem:hover {
    color:#619AE5;
  }

  .tx-item {
    display: flex;
    justify-content: space-between;
    margin-bottom:14px;
    font-family: AvenirNext-Medium;
    font-size: 12px;
    width:100%;
    cursor: pointer;
  }
 
  .tx-item:hover span {
    color:#196BD8 !important;
  }
  
  .tx-item :first-child {
    flex: 0.6;
    overflow: hidden;
    text-overflow: ellipsis;
    color: #6F7781;
  }

  .tx-item :last-child {
    flex:0.4;
    text-align: right;
    font-family: AvenirNext-Medium;
    font-size: 12px;
    color: #000000;
  }

.left-footer {
  margin-top:20px;
}
</style>
