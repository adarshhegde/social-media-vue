<template>
  <div class="profile__small">
    <img src="../../assets/profile.jpg" />
    <p class="profile__name"> Adarsh Hegde </p>
   <p>
    <span class="profile__numbers"> 
        <span class="profile__numbers__label">
            Followers
        </span>    
        <span class="profile__numbers__value">
            69
        </span>    
    </span>
    <span class="profile__numbers"> 
        <span class="profile__numbers__label">
            Following
        </span>    
        <span class="profile__numbers__value">
            92
        </span>    
    </span>
    </p>
</div>
</template>

<script>
export default {
name:'ProfileSmall'
}
</script>

<style scoped lang="scss">
.profile__small{
    width:100%;
    height:auto;
    display:flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top:25pt;
    margin-bottom:20pt;
    
    img {
        width:72px;
        height:72px;
        border-radius:50%;
    }
    .profile__name{
        font-size:12pt;
        font-weight:500;
        color:#181818;
        margin:15px;
        filter:var(--text-filter);
    }
    .profile__numbers{
        display:inline-flex;
        flex-direction: column;
        justify-content: center;
        align-items:center;
        margin:5px 30px;
        letter-spacing: -0.3005pt;
        

        .profile__numbers__label{
            font-size:10pt;
            color:rgba(0, 29, 66, 0.767);
                    font-weight:500;
                    filter:var(--text-filter-label);
        margin:4px;
        }
        .profile__numbers__value{
            font-size:10pt;
            font-weight:400;
            color:rgba(16, 65, 129, 0.89);
        }
    }
}
</style>