### vtkScalarsToColors - Superclass for mapping scalar values to colors

### Description
vtkScalarsToColors is a general-purpose base class for objects that
convert scalars to colors. This include vtkLookupTable classes and
color transfer functions.  By itself, this class will simply rescale
the scalars.

The scalar-to-color mapping can be augmented with an additional
uniform alpha blend. This is used, for example, to blend a vtkActor's
opacity with the lookup table values.

Specific scalar values may be annotated with text strings that will
be included in color legends using \a SetAnnotations, \a SetAnnotation,
\a GetNumberOfAnnotatedValues, \a GetAnnotatedValue, \a GetAnnotation,
\a RemoveAnnotation, and \a ResetAnnotations.

This class also has a method for indicating that the set of
annotated values form a categorical color map; by setting \a
IndexedLookup to true, you indicate that the annotated values are
the only valid values for which entries in the color table should
be returned. In this mode, subclasses should then assign colors to
annotated values by taking the modulus of an annotated value's
index in the list of annotations with the number of colors in the
table.

### See Also
vtkLookupTable vtkColorTransferFunction