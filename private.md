---
layout: default
---

<script>
(function() {
    var password = "";
    var hash = "5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8"; // "password"의 SHA256 해시
    
    if (sessionStorage.getItem("authenticated") !== "true") {
        password = prompt("비밀번호를 입력하세요:");
        
        // 간단한 해시 함수 (실제로는 crypto API 사용 권장)
        crypto.subtle.digest('SHA-256', new TextEncoder().encode(password))
            .then(hashBuffer => {
                const hashArray = Array.from(new Uint8Array(hashBuffer));
                const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join('');
                
                if (hashHex === hash) {
                    sessionStorage.setItem("authenticated", "true");
                } else {
                    alert("비밀번호가 틀렸습니다.");
                    window.location.href = "/";
                }
            });
    }
})();
</script>

# 비공개 페이지

이 페이지는 비밀번호로 보호됩니다.

## 내용

여기에 비공개 내용을 작성하세요.
