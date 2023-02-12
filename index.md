# Good idea!

Here you can try stuff:

<input type="text" name="passphrase" id="passphrase" autocomplete="off">
<input type="button" onclick="decode()" value="Try decoding stuff">

<script src="https://bitwiseshiftleft.github.io/sjcl/sjcl.js"></script> 
<div id="result"></div>

<script>
    let messages = [
        "{\"iv\":\"yspZGhEn8/S+f34bKiv4mA==\",\"v\":1,\"iter\":10000,\"ks\":128,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"gqV8hDnPJpk=\",\"ct\":\"vCT1nLTjcTF53m71KYYevSGwzQAeuoXSe8Ofttvc5D3tdlouWcJo80/f/V+fC19jIHmNp6Q5kj+BZvwqR8PvrJv+to99A5eb9v+yf8ON4LIi782uTU4879hd4mmX7VFF9kDAMPoNxtpBQjVG0GNn8Xu6AS3vXLgY8yHseQPByk80QJinlmaF5v+ByW5XZvjiN6eFC/6p+WfaotoN9Bg5HMGTRhN+PS/jAu1kjHuOfgI=\"}",
        "{\"iv\":\"6bIpt8gGTtMmmS+/YOTTKg==\",\"v\":1,\"iter\":10000,\"ks\":128,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"lcuvW5ViyEk=\",\"ct\":\"PtFcVIfx/9pMFcPYIAnmwAhW7zm76T1jauQSqPLJUjwrmJWzsd5ZTg4LBVB//PXbHIOkMnsCYynfq4SKpPFbcgkfF389qyY+ZNPMhn1FCawXBRJzuslY8/qJe0HSSgOXvjx2fAbdnYwaUswzbbKfzoV6Yg4+J7QNAiS+m78=\"}",
        "{\"iv\":\"GUHXLmiqNp+nCunXDafCxA==\",\"v\":1,\"iter\":10000,\"ks\":128,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"Vz8GBbNkezA=\",\"ct\":\"DOXfB7PPeKm4dg81Q4/YMLJirH0Ribul+JGskIHbtWWM5tDsiwcFsw+Qhdu7tgadMw5ITA==\"}",
        "{\"iv\":\"aEFeOIFuNIKOkbILWfZLTQ==\",\"v\":1,\"iter\":10000,\"ks\":128,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"MytVoz5kRnQ=\",\"ct\":\"92qtqLg3QM6DuyE5X+wkG2ze+T1poSv88urEJ7OUhlTGxRWbDWXDwm6fO2XyuYp5zVe/OhFGS7/ENeYupASAilJh\"}",
        "{\"iv\":\"ExEh/3hbN5f+yVPO7drFIg==\",\"v\":1,\"iter\":10000,\"ks\":128,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"dA738N6INl4=\",\"ct\":\"wv2UIHUM0hSeNaw/buzCx8d99YFLLUJcvJlyvXFxRV3Refbi9ybMKY3QtnSW4dRIhSryTVjq9XOSGv8J5oH07ExA1B9Wr+RkSBQcFbGsHxlQo2pYuGJ4S3NSZuwFAqxo2v9D62Lw6djQ4+QFUUAk7hCuNoKPUw==\"}",
        ]
    function decode() {
        for (message in messages) {
            try {
                let decoded = sjcl.decrypt(document.getElementById("passphrase").value, message);
                if (decoded.startsWith("::::")) {
                    document.getElementById("result").innerHTML = decoded.slice(4);
                }
            }
            catch {}
        }
    };
</script>

