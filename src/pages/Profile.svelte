<script>
    import SvelteMarkdown from 'svelte-markdown'
    let source = "";
    function readTextFile(file)
    {
        var rawFile = new XMLHttpRequest();
        rawFile.open("GET", file, false);
        rawFile.onreadystatechange = function ()
        {
            if(rawFile.readyState === 4)
            {
                if(rawFile.status === 200 || rawFile.status == 0)
                {
                    source = rawFile.responseText;
                }
            }
        }
        rawFile.send(null);
    }
    readTextFile('./pages/Profile.md');
</script>

<main>
    <p>
        Tên: Nguyễn Hoàng Phú An
        Email: renannguyen@pm.me
    
        Học vấn: Đại học Sư phạm Kỹ thuật thành phố Hồ Chí Minh
        Kinh nghiệm: C/C++, Rust, Java
    
    </p>

    <a href="\assets\Renan___Resume_and_CV.pdf">Download CV</a>
    
    <SvelteMarkdown {source} renderers></SvelteMarkdown>
</main>

<style></style>