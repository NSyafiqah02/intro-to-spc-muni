df_filtered <- X022...022[X022...022$Machine == 3 & 
                              X022...022$Temperature == 338 & 
                              X022...022$Pressure == 200, ]
chart <- qcc(df_filtered$PartLength, type = "xbar.one", 
             title = paste0("Xbar.one Chart for PartLength (Machine ", 3, ")"),
             ylab = "PartLength", 
             xlab = "Observation Index")
data_to_plot <- data.frame(
    observation = 1:length(df_filtered$PartLength),
    part_length = df_filtered$PartLength
)
center_line <- chart$center
lcl <- chart$limits[1]
ucl <- chart$limits[2]
p_ggplot <- ggplot(data_to_plot, aes(x = observation, y = part_length)) +
    geom_line(color = "#0072B2") +
    geom_point(color = "#0072B2") +
    geom_hline(yintercept = center_line, linetype = "dashed", color = "#D55E00", size = 1) +
    geom_hline(yintercept = lcl, linetype = "dashed", color = "#009E73", size = 1) +
    geom_hline(yintercept = ucl, linetype = "dashed", color = "#CC79A7", size = 1) +
    annotate("text", x = max(data_to_plot$observation) * 0.9, y = ucl, label = "UCL", vjust = -0.5, color = "#CC79A7") +
    annotate("text", x = max(data_to_plot$observation) * 0.9, y = lcl, label = "LCL", vjust = 1.5, color = "#009E73") +
    annotate("text", x = max(data_to_plot$observation) * 0.9, y = center_line, label = "CL", vjust = -0.5, color = "#D55E00") +
    labs(title = paste0("Xbar.one Chart for PartLength (Machine ", 3, ")"),
         x = "Observation Index",
         y = "PartLength")) +
    theme_minimal() +
    theme(plot.title = element_text(size = 18, hjust = 0.5),
          axis.title = element_text(size = 18),
          axis.text = element_text(size = 14),
          panel.background = element_rect(fill = "white", colour = NA))
plotly_plot <- ggplotly(p_ggplot)
saveWidget(plotly_plot, file = "media/plots/xbar_one_chart_machine3.html", selfcontained = TRUE)
