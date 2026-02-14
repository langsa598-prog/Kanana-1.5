> Lightweight Colab demo for running Kakao's Kanana LLM with 4-bit quantization.

이 프로젝트는 Hugging Face Hub에서 모델을 다운로드하기 위해 **HF_TOKEN 환경변수**가 필요합니다.

### Colab에서 설정 방법

1. 왼쪽 사이드바에서 **Secrets (🔑)** 클릭  
2. **+ New secret** 선택  
3. 아래처럼 입력

Name: HF_TOKEN
Value: your_huggingface_token


4. Notebook에서 자동으로 사용됩니다.

코드에서는 다음과 같이 사용합니다.

```python
import os
HF_TOKEN = os.getenv("HF_TOKEN")

⚠️ 보안을 위해 토큰을 코드 또는 GitHub에 직접 업로드하지 마세요.


# Kanana Text Generation Demo (Colab)

카카오의 Kanana 모델을 사용하여 코랩 환경에서 간단한 텍스트 생성 서비스를 실행한다.

## Pipeline

모델과 토크나이저를 로드한 뒤, 사용자 입력을 Chat Template 형태로 변환하고 토큰화한다.  
이 입력을 모델에 전달하여 텍스트를 생성(generate)하고, 생성된 토큰을 다시 사람이 읽을 수 있는 문장으로 디코딩한다.

4bit 양자화를 적용하여 GPU 메모리 사용량을 줄였으며, T4 GPU 환경에서도 실행 가능하도록 구성하였다. 모델은 사용자 질문을 기반으로 다음 토큰을 순차적으로 예측하며 응답을 생성한다.

## Output

최종 출력값은 모델이 생성한 자연어 텍스트 응답이며, 사용자의 입력에 이어지는 문장을 생성하는 간단한 대화형 서비스 형태로 동작한다.
