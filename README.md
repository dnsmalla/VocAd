# VocAd - Professional English Vocabulary Learning App

![VocAd Logo](app_logo.png)

**VocAd** is a modern iOS vocabulary learning app designed specifically for professionals, IT engineers, and language learners who want to master English vocabulary with smart flashcards and spaced repetition.

## 🌟 Features

### Core Learning Features
- **📚 Smart Flashcards**: Interactive flashcard system with word, meaning, translation (Japanese), and example sentences
- **🧠 Spaced Repetition (SRS)**: Intelligent review scheduling using the SM-2 algorithm
- **📊 Progress Tracking**: Comprehensive statistics, streaks, and learning analytics
- **🎯 Daily Challenges**: Gamified quizzes to test your knowledge
- **⭐ Favorites & Known Words**: Mark words you know well or want to review later
- **🔔 Smart Notifications**: Daily reminders to maintain your learning streak

### Professional Vocabulary Categories
1. **💻 IT & Engineering**
   - Software Development (deploy, refactor, debug, implement)
   - DevOps & Cloud (containerization, orchestration, pipeline)
   - Security (encryption, vulnerability, authentication)
   - Agile & Project Management (sprint, backlog, technical debt)
   - Technical phrases and idioms

2. **💼 Business & Professional**
   - Leadership & Management (stakeholder, leverage, synergy)
   - Finance & Metrics (ROI, revenue, profit margin)
   - Strategy & Planning (roadmap, pivot, competitive advantage)
   - Business idioms (think outside the box, touch base, bottom line)

3. **🏠 Daily Life & Conversation**
   - Common expressions and phrases
   - Casual conversations
   - Everyday idioms

4. **✈️ Travel & Tourism**
   - Travel vocabulary
   - Hotel & airport terms
   - Travel phrases

5. **📖 Academic & Education**
   - Study-related vocabulary
   - Academic terms
   - Educational phrases

6. **🎬 Entertainment & Media**
   - Movies, TV, and streaming
   - Music and arts
   - Entertainment slang

### Personalization
- **Level Selection**: Choose from Beginner, Intermediate, or Advanced
- **Interest-Based Learning**: Select categories relevant to your goals
- **Custom Word Lists**: Add your own vocabulary with translations and examples
- **Adjustable Daily Goals**: Set learning targets from 5-50 words per day

### User Experience
- **Beautiful UI**: Modern, clean interface with dark mode support
- **Progress Visualization**: Charts showing your learning activity
- **Achievement System**: Unlock badges and achievements as you learn
- **Multi-Mode Learning**: Study new words, review known words, or take challenges
- **Search & Filter**: Find words quickly by category, difficulty, or tags

## 📱 Screenshots

[Add screenshots here when available]

## 🚀 Getting Started

### Prerequisites
- iOS 16.0 or later
- Xcode 15.0 or later
- Swift 5.9 or later

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/VocAd.git
cd VocAd
```

2. Open the project in Xcode:
```bash
open VocAd/Notiq/Notiq.xcodeproj
```

3. Build and run the project:
   - Select your target device or simulator
   - Press `Cmd + R` to build and run

### First Launch

1. **Onboarding**: Select your current English level (Beginner/Intermediate/Advanced)
2. **Choose Interests**: Pick categories you want to focus on (IT, Business, Daily Life, etc.)
3. **Set Daily Goal**: Choose how many words you want to learn per day (5-50)
4. **Start Learning**: Begin your vocabulary journey!

## 🎯 How to Use

### Learning New Words
1. Tap "Learn New" on the home screen
2. Review flashcards with word, meaning, translation, and example
3. Rate how well you knew the word (Again/Hard/Good/Easy)
4. Words are scheduled for review based on your performance

### Reviewing
1. Check "Review" tab for words due for review
2. Filter by "Due Today", "Favorites", or "Difficult"
3. Complete review sessions to reinforce your memory

### Daily Challenge
1. Take daily quiz challenges to test your knowledge
2. Answer multiple choice, fill-in-the-blank, and translation questions
3. Track your score and accuracy

### Adding Custom Words
1. Go to Settings → "Add Custom Word"
2. Enter word/phrase, meaning, translation, and example sentence
3. Choose category, difficulty, and tags
4. Your custom words appear in your vocabulary list

## 🧠 Spaced Repetition Algorithm

VocAd uses the **SM-2 (SuperMemo 2)** algorithm for optimal review scheduling:

- **Quality Ratings**: 0-5 scale
  - 0-2: Incorrect/Difficult → Reset interval
  - 3: Correct with difficulty → Moderate increase
  - 4: Correct → Standard increase
  - 5: Perfect/Easy → Maximum increase

- **Review Intervals**:
  - First review: 1 day
  - Second review: 6 days
  - Subsequent reviews: Previous interval × ease factor

- **Ease Factor**: Dynamically adjusted based on your performance (1.3 - 3.0)

## 📊 Statistics & Progress

### Tracked Metrics
- **Words Learned**: Total vocabulary mastered
- **Review Count**: Total reviews completed
- **Accuracy Rate**: Percentage of correct answers
- **Current Streak**: Consecutive days of study
- **Longest Streak**: Record streak achieved
- **Study Time**: Time spent learning
- **Category Progress**: Breakdown by interest area

### Achievements
Unlock achievements by:
- Learning your first word
- Reaching milestones (10, 50, 100+ words)
- Maintaining streaks (7, 30 days)
- Completing reviews
- Mastering phrases

## 🛠️ Technical Stack

### Technologies
- **Language**: Swift 5.9
- **Framework**: SwiftUI
- **iOS Version**: iOS 16.0+
- **Architecture**: MVVM pattern
- **Data Persistence**: UserDefaults (can be migrated to Core Data)
- **Notifications**: UserNotifications framework
- **Charts**: Swift Charts

### Project Structure
```
VocAd/
├── VocAdApp.swift              # Main app entry point
├── Models/
│   └── DataModels.swift        # Data structures
├── Managers/
│   ├── DataManager.swift       # Vocabulary management
│   ├── UserProgressManager.swift # Progress tracking
│   └── NotificationManager.swift # Notification handling
├── Views/
│   ├── OnboardingView.swift    # Initial setup
│   ├── HomeView.swift          # Main dashboard
│   ├── FlashcardSessionView.swift # Learning session
│   ├── ReviewView.swift        # Review interface
│   ├── CategoriesView.swift    # Browse categories
│   ├── ProgressView.swift      # Statistics
│   ├── DailyChallengeView.swift # Quiz challenges
│   ├── SettingsView.swift      # App settings
│   ├── AchievementsView.swift  # Achievement display
│   └── CustomWordsListView.swift # User's custom words
└── Data/
    ├── SampleData.swift        # Built-in vocabulary
    └── ProfessionalVocabulary.swift # Professional terms
```

## 📦 Data Model

### Core Models
- `VocabularyItem`: Word/phrase with meaning, translation, example, category
- `VocabularyProgress`: User's progress for each word (reviews, accuracy, schedule)
- `UserProfile`: User settings, level, interests, statistics
- `StudySession`: Record of learning sessions
- `Achievement`: Unlockable milestones

## 🎨 Customization

### Adding New Vocabulary
Edit `ProfessionalVocabulary.swift` to add more words:

```swift
VocabularyItem(
    word: "your_word",
    meaning: "English definition",
    translation: "日本語訳",
    exampleSentence: "Example sentence using the word.",
    category: .itEngineering,
    difficulty: .intermediate,
    tags: ["tag1", "tag2"],
    isPhrase: false
)
```

### Modifying Categories
Add new categories in `DataModels.swift`:

```swift
enum InterestCategory: String, Codable, CaseIterable {
    case yourCategory = "Your Category Name"
    // ...
    var icon: String {
        case .yourCategory: return "icon.name"
    }
}
```

## 📈 Roadmap & Future Enhancements

### Planned Features
- [ ] Audio pronunciation (TTS or embedded audio files)
- [ ] Voice recording for practice
- [ ] Cloud sync across devices (Firebase/CloudKit)
- [ ] Social features (compare with friends, leaderboards)
- [ ] More gamification (levels, badges, rewards)
- [ ] Speech recognition for pronunciation practice
- [ ] CSV import/export for vocabulary
- [ ] Multiple language support (not just Japanese)
- [ ] Widgets for home screen
- [ ] Apple Watch companion app
- [ ] Premium features (advanced analytics, unlimited custom words)

### Version History
- **v1.0.0** (2025-11-12): Initial release
  - Core flashcard system
  - Spaced repetition algorithm
  - 6 vocabulary categories
  - 150+ professional terms
  - Progress tracking
  - Daily challenges
  - Custom word lists
  - Achievements

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Your Name**
- IT Engineer based in Tokyo
- Passionate about language learning and mobile development

## 🙏 Acknowledgments

- Inspired by spaced repetition apps like Anki and Memrise
- SuperMemo algorithm by Piotr Woźniak
- Professional vocabulary compiled from real-world usage

## 📞 Support

- Email: support@vocad.app
- Issues: [GitHub Issues](https://github.com/yourusername/VocAd/issues)
- Documentation: [Wiki](https://github.com/yourusername/VocAd/wiki)

## 🌐 Localization

Currently supports:
- English (UI)
- Japanese (Translations)

Want to add more languages? Contributions welcome!

---

**Made with ❤️ for professionals learning English**

#vocabulary #english #learning #ios #swift #swiftui #spaced-repetition #professional-english

