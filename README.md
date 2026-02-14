```markdown
> Lightweight Colab demo for running Kakao's Kanana LLM with 4-bit quantization.

이 프로젝트는 Hugging Face Hub에서 모델을 다운로드하기 위해 **HF_TOKEN 환경변수**가 필요합니다.

### Colab에서 설정 방법 (추천)

1. 왼쪽 사이드바에서 **Secrets (🔑)** 클릭  
2. **+ New secret** 선택  
3. 아래처럼 입력

```

Name: HF_TOKEN
Value: your_huggingface_token

````

4. Notebook에서 자동으로 사용됩니다.

코드에서는 다음과 같이 사용합니다.

```python
import os
HF_TOKEN = os.getenv("HF_TOKEN")
````

⚠️ 보안을 위해 토큰을 코드 또는 GitHub에 직접 업로드하지 마세요.

```

---
```
