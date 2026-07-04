LSL <- 45
USL <- 55
df_filtered <- X022...022[X022...022$Machine == 3 & 
                              X022...022$Temperature == 338 & 
                              X022...022$Pressure == 200, ]
png(filename = "media/plots/capability_machine3.png", width = 800, height = 600)
qcc_obj <- qcc(df_filtered$PartLength, type = "xbar.one", plot = FALSE)
process.capability(qcc_obj, spec.limits = c(LSL, USL),
                   target = 50,
                   nsigmas = 3)
title(main = paste0("Process Capability for PartLength (Machine ", 3, ")"))
dev.off()

