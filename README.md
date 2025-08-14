# 1911import openai

# إعداد مفتاح API الخاص بـ OpenAI
openai.api_key = "YOUR_API_KEY"

def generate_resume(name, education, experience, skills, languages):
    prompt = f"""
    قم بإنشاء سيرة ذاتية احترافية بناءً على المعلومات التالية:
    الاسم: {name}
    التعليم: {education}
    الخبرات العملية: {experience}
    المهارات: {skills}
    اللغات: {languages}
    """
    response = openai.Completion.create(
        engine="text-davinci-003",
        prompt=prompt,
        max_tokens=500
    )
    return response.choices[0].text.strip()

# مثال على الاستخدام
resume = generate_resume(
    name="محمد أحمد",
    education="بكالوريوس في علوم الحاسب من جامعة الملك سعود",
    experience="مبرمج في شركة XYZ لمدة 3 سنوات",
    skills="Python, JavaScript, SQL",
    languages="العربية: ممتاز، الإنجليزية: جيد جدًا"
)
print(resume)
