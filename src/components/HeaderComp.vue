<template>
  <header>
    <nav class="fixed-top header-menu">
      <div class="container">
        <span class="logo">
          <router-link to="/">IGSJ</router-link>
        </span>
        <span>
          <input class="search" type="text" placeholder="로라로라 × 재유 최대 10% 할인"/>
        </span>
        <span class="rank_bar">
          <p class="rank">{{rank}}</p>
          <router-link to="#" class="product">{{product}}</router-link>
        </span>
      </div>
      <div class="menus">
        <router-link to="#">랭킹</router-link>
        <router-link to="#">업데이트</router-link>
        <router-link to="#">코디</router-link>
        <router-link to="#">세일</router-link>
        <router-link to="#">스페셜</router-link>
        <router-link to="#">매거진</router-link>
        <router-link to="#">TV</router-link>
        <router-link to="#">이벤트</router-link>     
        <router-link to="#">브랜드</router-link>
      </div>
    </nav>
    <nav class="fixed-top header-submenu">
      <router-link to="/login"><button class="login_btn">로그인</button></router-link>
      <router-link to="#">마이페이지</router-link>
      <router-link to="#">최근 본 상품</router-link>
      <router-link to="#" style="color:red;">좋아요</router-link>
      <router-link to="#">장바구니</router-link>
      <router-link to="#">주문배송조회</router-link>
      <router-link to="#">고객센터</router-link>
    </nav>
  </header>
</template>

<script>
export default {
  data () {
    return {
      rank: 1,
      product:'상품',
      rankArr: ['니트', '가디건', '슬랙스', '샌들', '블라우스', '스커트', '맨투맨', '후드', '트레이닝', '재킷'],
      fn_rankShow: null
    }
  },
  mounted(){
    this.product=this.rankArr[Number(this.rank)-1]
    this.rankSetter()
  },
  methods: {
    rankSetter(){
      setInterval(()=>{
        this.rank++
        if(this.rank>10) this.rank=1
        this.product=this.rankArr[Number(this.rank)-1]
      }, 2000)
    }
  }
}
</script>

<style scoped>
  header {
    width: 100%;
  }
  .fixed-top {
    min-width: 1400px;
  }
  .header-menu {
    display:flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 70px;
    background: black;
    padding: 20px;
  }
  .container {
    display:flex;
    justify-content: left;
    align-items: center;
    padding: 0;
  }
  .logo a {
    color: white;
    font-size: 40px;
    margin-right: 20px;
    text-decoration: none;
  }
  .search {
    height: 30px;
    width: 300px;
    margin: 10px 0 10px 6px;
    border: none;
    outline: none;
  }
  .rank_bar {
    width: 350px;
    height: 30px;
    text-align: left;
    font-size: 20px;
  }
  .rank {
    width: 20px;
    display: inline;
    color: white;
    font-weight: bold;
    margin: 0 20px;
  }
  .product {
    width: 300px;
    display: inline;
    text-decoration: none;
    color: white;
    font-weight: bold;
  }
  .menus {
    width: 700px;
    display:flex;
    justify-content:space-between;
    align-items:center;
  }
  .menus a {
    text-decoration: none;
    color: white;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
  }
  .header-submenu {
    margin-top: 70px;
    width: 100%;
    height: 56px;
    background: white;
    border-bottom: 1px solid lightgrey;
    display: flex;
    justify-content: left;
    align-items: center;
  }
  .header-submenu a {
    font-size: 12px;
    text-decoration: none;
    color: black;
    font-weight: bold;
  }
  .header-submenu a:hover {
    text-decoration: underline;
  }
  .header-submenu a::after {
    content: "|";
    color: lightgrey;
    font-size: 10px;
    margin: 0 10px;
  }
  .header-submenu a:first-child::after {
    content: "";
    margin-left: 0;
  }
  .header-submenu a:last-child::after {
    content: "";
    margin-right: 0;
  }
  .login_btn {
    width: 160px;
    height: 30px;
    font-size: 12px;
    border: 1px solid black;
    background: none;
    margin: 0 16px;
  }
  .login_btn:hover {
    border: 1px solid black;
    background: black;
    color: white;
  }
</style>
