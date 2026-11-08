## Dlaczego przy SeekBar nie dało się użyć lambdy, a przy CheckBox tak?

Interfejs `SeekBar.OnSeekBarChangeListener` zawiera **trzy metody abstrakcyjne**:
- `onProgressChanged()`
- `onStartTrackingTouch()`
- `onStopTrackingTouch()`

Ponieważ interfejs ma więcej niż jedną metodę, nie jest to interfejs SAM (Single Abstract Method).  
W Javie (i w Kotlinie) lambdy działają tylko z interfejsami posiadającymi dokładnie jedną metodę abstrakcyjną.  
Dlatego przy `SeekBar` trzeba użyć pełnej klasy anonimowej:
