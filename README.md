# LoL-Player-stats-Analyzer

# Overview
This project is a specialized data extraction tool designed to interface with the Riot Games API. It allows users to track and analyze the performance of high-ranking players in the EUW (Europe West) region. By simply inputting a Riot ID (Name and Tagline), the script automatically retrieves match history, processes performance metrics, and exports a structured report into an Excel spreadsheet.

# Problem Solved
During development, we addressed a significant technical hurdle: Library Version Disparity. Many standard wrappers like riotwatcher do not natively support the most recent Riot ID account structures in older environments. To solve this, I implemented a hybrid architecture that uses:

Direct HTTP Requests (requests): To bypass library limitations and fetch account PUUIDs directly from Riot’s account servers.

SDK Integration (riotwatcher): To handle complex match-specific data extraction and rate-limiting logic.

# Core Functionality
Player Identification: Converts public Riot IDs (e.g., Agurin#EUW) into unique internal PUUIDs.

Data Aggregation: Iterates through the most recent match history to pull raw JSON data for each game.

Metric Calculation: Computes live KDA (Kills, Deaths, Assists) and formats game outcomes (Win/Loss).

Excel Automation: Uses Pandas and Openpyxl to transform raw API responses into a clean, human-readable table containing:

· Match ID

· Champion Played

· Game Result

· KDA Ratio

· Total Gold Earned

· In-game Position (Role)

# Technologies Used
Language: Python 3

Data Processing: Pandas

APIs: Riot Games Developer API (Account-V1 & Match-V5)

Networking: Requests (for custom API headers and Direct GET calls)

File I/O: Openpyxl (Excel Engine)
