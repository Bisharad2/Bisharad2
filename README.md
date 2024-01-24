class QuizQuestion:
    def __init__(self, question, options, correct_answer):
        self.question, self.options, self.correct_answer = question, options, correct_answer

    def is_correct(self, user_answer):
        return user_answer == self.correct_answer


def run_quiz(questions):
    score = 0
    for i, question in enumerate(questions, 1):
        print(f"\nQuestion {i}: {question.question}")
        for j, option in enumerate(question.options, 1):
            print(f"{j}. {option}")

        user_answer = int(input("Your answer: "))
        if question.is_correct(user_answer):
            print("Correct!")
            score += 1
        else:
            print(f"Wrong! Correct answer: {question.correct_answer}")

    print(f"\nQuiz completed! Your score: {score}/{len(questions)}")


# Example usage:
questions = [
    QuizQuestion("Capital of France?", ["Paris", "Berlin", "London"], 1),
    QuizQuestion("Red Planet?", ["Earth", "Mars", "Venus"], 2),
    QuizQuestion("Largest mammal?", ["Elephant", "Blue Whale", "Giraffe"], 2),
]

run_quiz(questions)
