from textblob import TextBlob

def analyze_mood(user_input):
    # 텍스트 감정 분석
    analysis = TextBlob(user_input)
    polarity = analysis.polarity  # -1.0 ~ 1.0 (감정 점수)

    # 결과 분류
    if polarity > 0.2:
        return "긍정적인 상태입니다. 계속 좋은 생각을 유지하세요!"
    elif polarity < -0.2:
        return "우울한 경향이 있습니다. 전문 상담을 고려해보세요."
    else:
        return "중립적인 상태입니다. 더 많은 감정 표현을 시도해보세요."

# 메인 실행
print("안녕하세요! 심리 상태를 확인해드립니다. 자유롭게 입력해주세요.")
while True:
    user_input = input(">> ")
    if user_input.lower() in ["종료", "exit", "quit"]:
        print("프로그램을 종료합니다.")
        break
    result = analyze_mood(user_input)
    print(f"분석 결과: {result}")
