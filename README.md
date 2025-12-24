# 🏏 IPL Analysis (2008-2025) - Power BI Dashboard

[![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-yellow.svg)](https://powerbi.microsoft.com/)
[![Data](https://img.shields.io/badge/Data-CSV-blue.svg)]()
[![IPL](https://img.shields.io/badge/IPL-2008--2025-orange.svg)]()

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Data Sources](#data-sources)
- [Data Model](#data-model)
- [Key Metrics & Measures](#key-metrics--measures)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Analytics Capabilities](#analytics-capabilities)
- [Technical Specifications](#technical-specifications)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Overview

This Power BI project provides **comprehensive analytics for the Indian Premier League (IPL)** spanning from **2008 to 2025**. The dashboard delivers in-depth cricket analytics through an integrated data model combining match-level statistics, ball-by-ball granular data, player profiles, and team information.

### Key Highlights
- ✅ **17+ IPL Seasons** of historical data (2008-2025)
- ✅ **400,000+ ball-by-ball records** for detailed analysis
- ✅ **1,000+ matches** across all seasons
- ✅ **600+ player profiles** with playing styles
- ✅ **34 DAX measures** for advanced analytics
- ✅ **Interactive visualizations** with team/player images

---

## ✨ Features

### 🏆 Tournament Analytics
- Season winners and runners-up tracking
- Points table and team standings
- Stage-wise performance (league, playoffs, finals)
- Tournament progression analysis

### 👤 Player Performance
- **Orange Cap**: Top run-scorers by season
- **Purple Cap**: Leading wicket-takers
- Centuries and half-centuries tracking
- Most 4s and 6s hitters with player images
- Batting and bowling style analysis

### 🏟️ Match Insights
- Venue and city-wise statistics
- Toss impact analysis
- Win margin analysis (runs/wickets)
- Player of the match trends
- Match type and format breakdowns

### 📊 Detailed Metrics
- Ball-by-ball match reconstruction
- Over-by-over scoring patterns
- Economy rates and strike rates
- Wicket analysis and dismissal types
- Extras and penalty analysis

---

## 📁 Data Sources

### 1. 🎯 **ball_by_ball_data.csv**
Granular ball-by-ball data capturing every delivery in IPL matches.

| Column | Type | Description |
|--------|------|-------------|
| `season_id` | Integer | IPL season identifier |
| `match_id` | Integer | Unique match identifier |
| `batter` | Text | Batsman facing the delivery |
| `bowler` | Text | Bowler delivering the ball |
| `non_striker` | Text | Non-striking batsman |
| `team_batting` | Text | Batting team name |
| `team_bowling` | Text | Bowling team name |
| `over_number` | Integer | Over number (0-19 for T20) |
| `ball_number` | Integer | Ball number within the over |
| `batter_runs` | Integer | Runs scored by batsman |
| `extras` | Integer | Extra runs (wide, no-ball, etc.) |
| `total_runs` | Integer | Total runs from the delivery |
| `batsman_type` | Text | Batting style (RHB/LHB) |
| `bowler_type` | Text | Bowling style (pace/spin) |
| `player_out` | Text | Name of dismissed player |
| `fielders_involved` | Text | Fielders involved in dismissal |
| `is_wicket` | Boolean | Wicket fell on this ball |
| `is_wide_ball` | Boolean | Wide ball flag |
| `is_no_ball` | Boolean | No ball flag |
| `is_leg_bye` | Boolean | Leg bye flag |
| `is_bye` | Boolean | Bye flag |
| `is_penalty` | Boolean | Penalty runs flag |
| `wide_ball_runs` | Integer | Runs from wide |
| `no_ball_runs` | Integer | Runs from no ball |
| `leg_bye_runs` | Integer | Leg bye runs |
| `bye_runs` | Integer | Bye runs |
| `penalty_runs` | Integer | Penalty runs |
| `wicket_kind` | Text | Type of dismissal |
| `is_super_over` | Boolean | Super over flag |
| `innings` | Integer | Innings number (1 or 2) |

**Total Records:** ~400,000+ deliveries  
**Use Cases:** Strike rate, economy rate, phase analysis, wicket patterns

---

### 2. 🏆 **ipl_matches_data.csv**
Match-level aggregated data with match outcomes and metadata.

| Column | Type | Description |
|--------|------|-------------|
| `match_id` | Integer | Unique match identifier |
| `season_id` | Integer | IPL season identifier |
| `balls_per_over` | Integer | Balls per over (usually 6) |
| `city` | Text | City where match was played |
| `match_date` | Date | Date of the match |
| `event_name` | Text | Tournament/event name |
| `match_number` | Text | Match number in season |
| `gender` | Text | Gender category (male/female) |
| `match_type` | Text | Match type (league/playoff) |
| `format` | Text | Match format (T20) |
| `overs` | Integer | Total overs per innings |
| `season` | Text | Season year (e.g., "2024") |
| `team_type` | Text | Team category |
| `venue` | Text | Stadium/venue name |
| `toss_winner` | Text | Team that won the toss |
| `team1` | Text | First team |
| `team2` | Text | Second team |
| `toss_decision` | Text | Bat/Field decision |
| `match_winner` | Text | Winning team |
| `win_by_runs` | Text | Victory margin in runs |
| `win_by_wickets` | Text | Victory margin in wickets |
| `player_of_match` | Text | Player of the match |
| `result` | Text | Match result description |
| `stage` | Text | Tournament stage |

**Total Records:** ~1,000+ matches  
**Use Cases:** Team performance, venue analysis, toss impact, tournament standings

---

### 3. 👥 **players-data-updated.csv**
Player master data with profiles and playing styles.

| Column | Type | Description |
|--------|------|-------------|
| `player_id` | Integer | Unique player identifier |
| `player_name` | Text | Player display name |
| `bat_style` | Text | Batting style (RHB/LHB) |
| `bowl_style` | Text | Bowling style (pace/spin/none) |
| `field_pos` | Text | Preferred fielding position |
| `player_full_name` | Text | Player's full name |
| `player_name2` | Text | Alternative player name |
| `player_image` | Text | URL/path to player image |

**Total Records:** ~600+ players  
**Use Cases:** Player profiling, style-based analysis, visual representation

---

### 4. 🏅 **teams_data.csv**
Team master data with branding assets.

| Column | Type | Description |
|--------|------|-------------|
| `team_id` | Integer | Unique team identifier |
| `team_name` | Text | Full team name |
| `team_name_short` | Text | Abbreviated team name |
| `image_url` | Text | URL/path to team logo |

**Total Records:** 10-15 franchises  
**Use Cases:** Team identification, logo display, team filtering

---

## 🔗 Data Model

### Relationship Structure

```
ball_by_ball_data (Fact Table)
    ├── match_id → ipl_matches_data[match_id] (Many-to-One)
    ├── season_id → ipl_matches_data[season_id] (Many-to-One)
    ├── batter → players-data-updated[player_name] (Many-to-One)
    ├── bowler → players-data-updated[player_name] (Many-to-One)
    └── team_batting → teams_data[team_name] (Many-to-One)

ipl_matches_data (Dimension Table)
    ├── team1 → teams_data[team_name] (Many-to-One)
    ├── team2 → teams_data[team_name] (Many-to-One)
    └── match_date → Date Table (Time Intelligence)

players-data-updated (Dimension Table)
teams_data (Dimension Table)
```

### Model Type
- **Schema:** Star Schema
- **Storage Mode:** Import
- **Refresh:** Manual/Scheduled

---

## 📊 Key Metrics & Measures

### 🏆 Tournament Awards (8 measures)
- `Season Winner` - Champion of each IPL season
- `Season Winner Logo` - Winner's team logo
- `RunnerUp` - Runner-up team
- `RunnerUp Logo` - Runner-up team logo

### 📈 Aggregated Statistics (5 measures)
- `Total Matches` - Total number of matches
- `Total Teams` - Number of participating teams
- `Total Venues` - Unique venues count
- `Total 6's` - Aggregate sixes hit
- `Total 4's` - Aggregate fours hit

### 🏏 Batting Achievements (2 measures)
- `Centuries` - Total 100+ scores
- `Half centuries` - Total 50+ scores

### 🥇 Orange Cap - Top Run Scorer (4 measures)
- `Orange Cap Holder` - Player with most runs
- `Orange Cap Holder Runs` - Total runs scored
- `Orange Cap Holder TeamName` - Player's team
- `Orange Cap Image` - Player image

### 🎯 Purple Cap - Top Wicket Taker (4 measures)
- `Purple Cap Holder` - Player with most wickets
- `Purple cap Holder Wickets` - Total wickets taken
- `Purple Cap Holder TeamName` - Player's team
- `Purple Cap Holder Image` - Player image

### 4️⃣ Most Fours (4 measures)
- `Top Fours Player Name` - Player with most 4s
- `Top Fours Count` - Number of fours
- `Top Fours Team Name` - Player's team
- `Top Fours Player Image` - Player image

### 6️⃣ Most Sixes (4 measures)
- `Total Six Count` - Total sixes by player
- `Top Six Player Name` - Player with most 6s
- `Top Six Team Name` - Player's team
- `Top Six Player Image` - Player image

### 🏅 Team Performance (7 measures)
- `Matches played` - Total matches by team
- `Matches Won` - Victories count
- `Lost Matches` - Defeats count
- `No Result Played` - Abandoned matches
- `Tie Played` - Tied matches
- `Total Points` - Points table score
- `IPL Season` - Season context

**Total DAX Measures:** 34

---

## 🚀 Setup Instructions

### Prerequisites
- **Power BI Desktop** (latest version recommended)
- **Minimum 4GB RAM** for model processing
- **CSV file reader** capability

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/ipl-analysis.git
   cd ipl-analysis
   ```

2. **Prepare Data Files**
   - Ensure all CSV files are in the `data` folder:
     - `ball_by_ball_data.csv`
     - `ipl_matches_data.csv`
     - `players-data-updated.csv`
     - `teams_data.csv`

3. **Open Power BI File**
   - Open `IPL Analysis (2008-2025).pbix` in Power BI Desktop

4. **Update Data Source Paths**
   - Go to **Transform Data** > **Data Source Settings**
   - Update file paths to match your local directory structure
   - Example: `C:\Users\YourName\ipl-analysis\data\`

5. **Refresh Data**
   - Click **Refresh** in the Home ribbon
   - Wait for data to load (may take 2-5 minutes)

6. **Verify Relationships**
   - Go to **Model View**
   - Ensure all relationships are active and correct

---

## 💡 Usage

### Dashboard Navigation
1. **Overview Page** - High-level tournament statistics
2. **Team Performance** - Team-wise analysis and comparisons
3. **Player Statistics** - Individual player performance
4. **Match Analysis** - Detailed match breakdowns
5. **Venue Insights** - Ground and city statistics

### Filters & Slicers
- **Season Filter** - Analyze specific IPL seasons
- **Team Filter** - Focus on particular franchises
- **Player Filter** - Track individual players
- **Venue Filter** - Location-based analysis

### Interactive Features
- Click on visual elements to cross-filter
- Hover over data points for tooltips
- Use drill-through for detailed analysis
- Export visuals to PowerPoint/PDF

---

## 📈 Analytics Capabilities

### Strategic Insights
- **Win Probability Analysis** - Factors influencing match outcomes
- **Toss Impact** - Bat/Field decision effectiveness
- **Home Advantage** - Team performance at home venues
- **Player Combinations** - Best batting/bowling partnerships

### Performance Metrics
- **Strike Rates** - Batsman scoring efficiency
- **Economy Rates** - Bowler effectiveness
- **Boundary Percentage** - Proportion of runs via 4s/6s
- **Dot Ball Analysis** - Pressure creation metrics

### Trend Analysis
- **Season-over-Season** - Performance evolution
- **Career Trajectories** - Player growth patterns
- **Format Adaptability** - Performance across match types
- **Phase Analysis** - Powerplay, middle overs, death overs

---

## 🛠️ Technical Specifications

### Power BI Details
- **Version:** Power BI Desktop (2023+)
- **Compatibility Level:** 1550
- **Storage Mode:** Import
- **Language:** DAX for measures, M for transformations

### Data Characteristics
- **Total Size:** ~50-100 MB (raw CSV files)
- **Model Size:** ~150-200 MB (Power BI)
- **Refresh Duration:** 2-5 minutes
- **Query Performance:** Sub-second for most visuals

### ETL Process
- **Tool:** Power Query (M Language)
- **Transformations:** 
  - Header promotion
  - Data type conversions
  - Column renaming (minimal)
- **Data Quality:** Clean source, minimal null handling

### Performance Optimization
- ✅ Star schema implementation
- ✅ Proper relationships with cardinality
- ✅ Calculated columns avoided where possible
- ✅ Aggregations at measure level
- ✅ Date table for time intelligence

---

## 📝 Data Update Process

### Adding New Season Data

1. **Update CSV Files**
   - Add new rows to existing CSV files
   - Maintain column structure and data types
   - Ensure match_id and player_id uniqueness

2. **Refresh Power BI**
   - Open the .pbix file
   - Click **Refresh** on the Home ribbon
   - Verify new data appears in visuals

3. **Validate Measures**
   - Check Orange/Purple Cap calculations
   - Verify season winner updates
   - Test all DAX measures

4. **Publish Updates**
   - Commit updated CSV files to repository
   - Update .pbix file
   - Document changes in release notes

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork the Repository**
2. **Create a Feature Branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit Changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to Branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Contribution Areas
- 📊 New visualizations and dashboards
- 🔍 Additional DAX measures
- 🐛 Bug fixes and optimizations
- 📖 Documentation improvements
- 🎨 UI/UX enhancements

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Data Source:** IPL official statistics and cricket data providers
- **Power BI Community** for DAX patterns and best practices
- **Cricket Analytics Community** for domain insights

---

## 📞 Contact & Support

For questions, suggestions, or issues:
- **GitHub Issues:** [Open an issue](https://github.com/yourusername/ipl-analysis/issues)
- **Email:** your.email@example.com
- **LinkedIn:** [Your Profile](https://linkedin.com/in/yourprofile)

---

## 🎯 Roadmap

### Future Enhancements
- [ ] Real-time data integration via API
- [ ] Predictive analytics (match outcome prediction)
- [ ] Player comparison tool
- [ ] Fantasy league point calculator
- [ ] Mobile-responsive Power BI App
- [ ] Python integration for advanced ML models
- [ ] Sentiment analysis from social media

---

## 📊 Sample Visuals

### Dashboard Preview
*(Add screenshots of your Power BI dashboards here)*

1. **Season Overview Dashboard**
2. **Player Performance Dashboard**
3. **Team Comparison Dashboard**
4. **Match Analysis Dashboard**

---

## 🔖 Version History

### v1.0.0 (Current)
- Initial release with 2008-2025 IPL data
- 34 DAX measures implemented
- 4 data sources integrated
- Star schema data model

---

## ⭐ Star This Repository

If you find this project useful, please consider giving it a star! ⭐

---

**Built with ❤️ for Cricket Analytics**

