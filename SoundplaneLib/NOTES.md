To configure libusb build on macOS:
- brew install libusb
- mkdir build; cd build
- CXXFLAGS=-std=c++11 cmake -DSP_USE_LIBUSB=yes ..

Port old mListener method calls to new api