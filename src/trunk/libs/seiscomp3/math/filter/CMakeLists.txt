SET(FILTER_SOURCES
	abs.cpp
	const.cpp
	cutoff.cpp
	biquad.cpp
	butterworth.cpp
	iirfilter.cpp
	iirintegrate.cpp
	iirdifferentiate.cpp
	average.cpp
	stalta.cpp
	taper.cpp
	rmhp.cpp
	chainfilter.cpp
	seismometers.cpp
)

SET(FILTER_HEADERS
	abs.h
	const.h
	cutoff.h
	biquad.h
	biquad.ipp
	butterworth.h
	butterworth.ipp
	iirfilter.h
	iirintegrate.h
	iirdifferentiate.h
	average.h
	stalta.h
	taper.h
	rmhp.h
	chainfilter.h
	op2filter.h
	op2filter.ipp
	seismometers.h
)

SC_SETUP_LIB_SUBDIR(FILTER)
