# Obsidian Wellness Templates

A comprehensive template system for tracking wellness and personal development in Obsidian. This system includes daily check-ins, weekly reviews, monthly reflections, and quarterly assessments. This is also a work-in-progress, and personal side-project, so expect things to not work seemlessly yet.

## Overview

This template system helps track:
- Daily energy levels and mood
- Sleep quality
- Physical activity
- Rest and recovery
- Social connections
- Nourishment (physical, mental, emotional)
- Gratitude practice
- Personal reflections

## Required Plugins

- [Templater](https://github.com/SilentVoid13/Templater): For template functionality and dynamic dates
- [Dataview](https://github.com/blacksmithgu/obsidian-dataview): For data visualization and tracking
- [Metadata Menu](https://github.com/mdelobelle/metadatamenu): For property management

## Setup Instructions

1. **Install Required Plugins**
   - Open Obsidian Settings
   - Go to Community Plugins
   - Browse and install the required plugins
   - Enable each plugin

2. **Template Setup**
   - Create a 'Templates' folder in your vault
   - Copy all template files into this folder
   - In Templater settings, set your template folder location

3. **Folder Structure**
   ```
   Your Vault/
   ├── Templates/
   │   ├── daily-template.md
   │   ├── weekly-template.md
   │   ├── monthly-template.md
   │   └── quarterly-template.md
   └── Daily Notes/
       └── YYYY/
           └── Month/
   ```

## Usage

### Daily Template
- Creates a new note for daily wellness tracking
- Automatically organizes notes by year/month
- Tracks:
  - Energy levels (1-5)
  - Mood
  - Sleep
  - Activities
  - Reflections

### Weekly Review
- Aggregates data from daily notes
- Provides insights on patterns
- Helps plan the upcoming week

### Monthly Review
- Shows trends and patterns
- Helps set monthly intentions
- Tracks progress on wellness goals

### Quarterly Assessment
- Uses a 360° wellness wheel
- Deep reflection on all wellness pillars
- Long-term trend analysis

## Customization

Templates can be customized by:
1. Modifying the frontmatter properties
2. Adjusting dataview queries
3. Adding or removing sections
4. Customizing rating scales

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Version History

- v1.0.0 - Initial release
  - Basic template structure
  - Daily, weekly, monthly, and quarterly templates
  - Dataview integration

## Planned Updates

- Enhanced data visualization
- Enhanced wellness metrics
- Increase automation, decrease user effort, especially with the properties updating

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Obsidian for such a robust tool
- [Papier, whose wellness journal inspired this project](https://www.papier.com/us/tulip-vase-42793)
- The Obsidian plugin developers, who made this possible 

## Support

For issues, questions, or suggestions:
1. Open an issue on GitHub
2. Check the Discussions tab
3. Review existing documentation
