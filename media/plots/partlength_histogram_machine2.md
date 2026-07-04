p <- ggplot(df_machine, aes(x = PartLength)) +
    geom_histogram(binwidth = 1, fill = "#0072B2", color = "white", alpha = 0.8) +
    labs(title = paste("Histogram of PartLength for Machine", machine_num), 
         x = "PartLength", 
         y = "Frequency")) +
    theme_minimal() +
    theme(plot.title = element_text(size = 18, hjust = 0.5),
          axis.title = element_text(size = 18),
          axis.text = element_text(size = 14),
          panel.background = element_rect(fill = "white", colour = NA))
plotly_plot <- ggplotly(p)
saveWidget(plotly_plot, file = "media/plots/partlength_histogram_machine2.html", selfcontained = TRUE)
