MiscCode
========
replaceNAs <- function(dataset, whatfun) {
  replace_these = ( is.na(dataset ) )
	ndataset = matrix(nrow = NROW(dataset), ncol = NCOL(dataset))
	for (i in 1:NCOL(dataset)){
	ndataset[,i] = replace(dataset[,i],which(is.na(dataset[,i]) == 1) ,whatfun(dataset[,i],na.rm = T))
	}
	colnames(ndataset)<-names(dataset)
	return(ndataset)
}

