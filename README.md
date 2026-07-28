body{
    font-family:Inter,Segoe UI,sans-serif;
    background:#0f172a;
    color:#e2e8f0;
    max-width:1200px;
    margin:auto;
    padding:40px;
    line-height:1.7;
}

.container{
    background:#111827;
    border:1px solid #1f2937;
    border-radius:18px;
    padding:40px;
}

.hero{
    text-align:center;
    padding:50px 20px;
}

.hero h1{
    font-size:3rem;
    margin-bottom:10px;
}

.hero p{
    color:#94a3b8;
}

.grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
    gap:20px;
    margin:40px 0;
}

.card{
    background:#1e293b;
    padding:25px;
    border-radius:15px;
    transition:.3s;
}

.card:hover{
    transform:translateY(-5px);
    background:#273549;
}

.tech{
    display:flex;
    flex-wrap:wrap;
    gap:10px;
}

.badge{
    background:#2563eb;
    padding:8px 16px;
    border-radius:999px;
}

img{
    max-width:100%;
    border-radius:12px;
}

footer{
    margin-top:60px;
    text-align:center;
    color:#94a3b8;
}
