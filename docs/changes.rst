Wand Changelog
==============

Version 0.3.8
-------------

Released on August 3, 2014.

- Fixed a bug that transparent background becomes filled with white
  when SVG is converted to other bitmap image format like PNG.  [:issue:`184`]
- Added :meth:`Image.negate() <wand.image.BaseImage.negate>` method.
  [:issue:`174` by Park Joon-Kyu]
- Fixed a segmentation fault on :meth:`Image.modulate()
  <wand.image.BaseImage.modulate>` method.
  [:issue:`173` by Ted Fung, :issue:`158`]
- Added suggestion to install freetype also if Homebrew is used.
  [:issue:`141`]
- Now :mimetype:`image/x-gif` also is determined as :attr:`animation`.
  [:issue:`181` by Juan-Pablo Scaletti]


Version 0.3.7
-------------

Released on March 25, 2014.

- A hotfix of debug prints made at 0.3.6.


Version 0.3.6
-------------

Released on March 23, 2014.

- Added :meth:`Drawing.rectangle() <wand.drawing.Drawing.rectangle>` method.
  :ref:`Now you can draw rectangles. <draw-rectangles>` [:issue:`159`]
- Added :attr:`Image.compression <wand.image.Image.compression>` property.
  [:issue:`171`]
- Added :func:`contextlib.nested()` function to :mod:`wand.compat` module.
- Fixed :exc:`UnicodeEncodeError` when :meth:`Drawing.text()
  <wand.drawing.Drawing.text>` method gives Unicode ``text`` argument
  in Python 2.  [:issue:`163`]
- Now it now allows to use Wand when Python is invoked with the ``-OO`` flag.
  [:issue:`169` by Samuel Maudo]


Version 0.3.5
-------------

Released on September 13, 2013.

- Fix segmentation fault on :meth:`Image.save() <wand.image.save>` method.
  [:issue:`150`]


Version 0.3.4
-------------

Released on September 9, 2013.

- Added :meth:`Image.modulate() <wand.image.BaseImage.modulate>` method.
  [:issue:`134` by Dan P. Smith]
- Added :attr:`Image.colorspace <wand.image.BaseImage.colorspace>` property.
  [:issue:`135` by Volodymyr Kuznetsov]
- Added :meth:`Image.unsharp_mask() <wand.image.BaseImage.unsharp_mask>`
  method.  [:issue:`136` by Volodymyr Kuznetsov]
- Added ``'jpeg:sampling-factor'`` option to :attr:`Image.options
  <wand.image.BaseImage.options>` dictionary (and :const:`~wand.image.OPTIONS`
  constant).  [:issue:`137` by Volodymyr Kuznetsov]
- Fixed ImageMagick shared library resolution on Arch Linux.
  [:issue:`139`, :issue:`140` by Sergey Tereschenko]
- Added :meth:`Image.sample() <wand.image.BaseImage.sample>` method.
  [:issue:`142` by Michael Allen]
- Fixed a bug that :meth:`Image.save() <wand.image.Image.save>` preserves
  only one frame of the given animation when file-like object is passed.
  [:issue:`143`, :issue:`145` by Michael Allen]
- Fixed searching of ImageMagick shared library with HDR support enabled.
  [:issue:`148`, :issue:`149` by Lipin Dmitriy]


Version 0.3.3
-------------

Released on August 4, 2013.  It's author's birthday.

- Added :meth:`Image.gaussian_blur() <wand.image.BaseImage.gaussian_blur>`
  method.
- Added :attr:`Drawing.stroke_color <wand.drawing.Drawing.stroke_color>`
  property.  [:issue:`129` by Zeray Rice]
- Added :attr:`Drawing.stroke_width <wand.drawing.Drawing.stroke_width>`
  property.  [:issue:`130` by Zeray Rice]
- Fixed a memory leak of :class:`~wand.color.Color` class.
  [:issue:`127` by Wieland Morgenstern]
- Fixed a bug that :meth:`Image.save() <wand.image.Image.save>` to stream
  truncates data.  [:issue:`128` by Michael Allen]
- Fixed broken :func:`~wand.display.display()` on Python 3.
  [:issue:`126`]


Version 0.3.2
-------------

Released on July 11, 2013.

- Fixed incorrect encoding of filenames.  [:issue:`122`]
- Fixed key type of :attr:`Image.metadata <wand.image.Image.metadata>`
  dictionary to :class:`str` from :class:`bytes` in Python 3.
- Fixed CentOS compatibility [:issue:`116`, :issue:`124` by Pierre Vanliefland]

  - Made :c:func:`DrawSetTextInterlineSpacing()` and
    :c:func:`DrawGetTextInterlineSpacing()` optional.
  - Added exception in drawing API when trying to use
    :c:func:`DrawSetTextInterlineSpacing()` and
    :c:func:`DrawGetTextInterlineSpacing()` functions when they are not
    available.
  - Added :exc:`~wand.exceptions.WandLibraryVersionError` class for
    library versions issues.


Version 0.3.1
-------------

Released on June 23, 2013.

- Fixed :exc:`~exceptions.ImportError` on Windows.


.. _changelog-0.3.0:

Version 0.3.0
-------------

Released on June 17, 2013.

.. seealso::

   :doc:`whatsnew/0.3`
      This guide introduces what's new in Wand 0.3.

- Now also works on Python 2.6, 2.7, and 3.2 or higher.
- Added :mod:`wand.drawing` module.  [:issue:`64` by Adrian Jung]
- Added :meth:`Drawing.get_font_metrics()
  <wand.drawing.Drawing.get_font_metrics>` method.
  [:issue:`69`, :issue:`71` by Cha, Hojeong]
- Added :meth:`Image.caption() <wand.image.BaseImage.caption>` method.
  [:issue:`74` by Cha, Hojeong]
- Added optional ``color`` parameter to :meth:`Image.trim()
  <wand.image.Image.trim>` method.
- Added :meth:`Image.border() <wand.image.Image.border>` method.
  [:commit:`2496d37f75d75e9425f95dde07033217dc8afefc` by Jae-Myoung Yu]
- Added ``resolution`` parameter to :meth:`Image.read() <wand.image.Image.read>`
  method and the constructor of :class:`~wand.image.Image`.
  [:issue:`75` by Andrey Antukh]
- Added :meth:`Image.liquid_rescale() <wand.image.BaseImage.liquid_rescale>`
  method which does `seam carving`__.  See also :ref:`seam-carving`.
- Added :attr:`Image.metadata <wand.image.Image.metadata>` immutable mapping
  attribute and :class:`~wand.image.Metadata` mapping type for it.
  [:issue:`56` by Michael Elovskikh]
- Added :attr:`Image.channel_images <wand.image.Image.channel_images>`
  immutable mapping attribute and :class:`~wand.image.ChannelImageDict`
  mapping for it.
- Added :attr:`Image.channel_depths <wand.image.Image.channel_depths>`
  immutable mapping attribute and :class:`~wand.image.ChannelDepthDict`
  mapping for it.
- Added :meth:`Image.composite_channel()
  <wand.image.BaseImage.composite_channel>` method.
- Added :meth:`Image.read() <wand.image.Image.read>` method.
  [:issue:`58` by Piotr Florczyk]
- Added :attr:`Image.resolution <wand.image.BaseImage.resolution>` property.
  [:issue:`58` by Piotr Florczyk]
- Added :meth:`Image.blank() <wand.image.Image.blank>` method.
  [:issue:`60` by Piotr Florczyk]
- Fixed several memory leaks.  [:issue:`62` by Mitch Lindgren]
- Added :class:`~wand.image.ImageProperty` mixin class to maintain
  a weak reference to the parent image.
- Ranamed :const:`wand.image.COMPOSITE_OPS` to
  :const:`~wand.image.COMPOSITE_OPERATORS`.
- Now it shows helpful error message when ImageMagick library cannot be
  found.
- Added IPython-specialized formatter.
- Added :const:`~wand.version.QUANTUM_DEPTH` constant.

- Added these properties to :class:`~wand.color.Color` class:

  - :attr:`~wand.color.Color.red_quantum`
  - :attr:`~wand.color.Color.green_quantum`
  - :attr:`~wand.color.Color.blue_quantum`
  - :attr:`~wand.color.Color.alpha_quantum`
  - :attr:`~wand.color.Color.red_int8`
  - :attr:`~wand.color.Color.green_int8`
  - :attr:`~wand.color.Color.blue_int8`
  - :attr:`~wand.color.Color.alpha_int8`

- Added :meth:`Image.normalize() <wand.image.Image.normalize>` method.
  [:issue:`95` by Michael Curry]
- Added :meth:`Image.transparent_color()
  <wand.image.BaseImage.transparent_color>` method.
  [:issue:`98` by Lionel Koenig]
- Started supporting resizing and cropping of GIF images.
  [:issue:`88` by Bear Dong, :issue:`112` by Taeho Kim]
- Added :meth:`Image.flip() <wand.image.BaseImage.flip>` method.
- Added :meth:`Image.flop() <wand.image.BaseImage.flop>` method.
- Added :attr:`Image.orientation <wand.image.BaseImage.orientation>` property.
  [:commit:`88574468a38015669dae903185fb328abdd717c0` by Taeho Kim]
- :exc:`wand.resource.DestroyedResourceError` becomes a subtype of
  :exc:`wand.exceptions.WandException`.
- :class:`~wand.color.Color` is now hashable, so can be used as a key of
  dictionaries, or an element of sets.  [:issue:`114` by klutzy]
- :class:`~wand.color.Color` has :attr:`~wand.color.Color.normalized_string`
  property.
- :class:`~wand.image.Image` has :attr:`~wand.image.BaseImage.histogram`
  dictionary.
- Added optional ``fuzz`` parameter to :meth:`Image.trim()
  <wand.image.Image.trim>` method.  [:issue:`113` by Evaldo Junior]

__ http://en.wikipedia.org/wiki/Seam_carving


Version 0.2.4
-------------

Released on May 28, 2013.

- Fix :exc:`~exceptions.NameError` in :attr:`Resource.resource
  <wand.resource.Resource.resource>` setter.
  [:issue:`89` forwareded from Debian bug report `#699064`__
  by Jakub Wilk]
- Fix the problem of library loading for Mac with Homebrew and Arch Linux.
  [:issue:`102` by Roel Gerrits, :issue:`44`]

__ http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=699064


Version 0.2.3
-------------

Released on January 25, 2013.

- Fixed a bug that :meth:`Image.transparentize()
  <wand.image.Image.transparentize>` method (and :meth:`Image.watermark()
  <wand.image.Image.watermark>` method which internally uses it) didn't
  work.
- Fixed segmentation fault occured when :attr:`Color.red
  <wand.color.Color.red>`, :attr:`Color.green <wand.color.Color.green>`,
  or :attr:`Color.blue <Wand.color.Color.blue>` is accessed.
- Added :attr:`Color.alpha <wand.color.Color.alpha>` property.
- Fixed a bug that format converting using :attr:`Image.format
  <wand.image.Image.format>` property or :meth:`Image.convert()
  <wand.image.Image.convert>` method doesn't correctly work
  to save blob.


Version 0.2.2
-------------

Released on September 24, 2012.

- A compatibility fix for FreeBSD.
  [`Patch`__ by Olivier Duchateau]
- Now :class:`~wand.image.Image` can be instantiated without any opening.
  Instead, it can take ``width``/``height`` and ``background``.
  [:issue:`53` by Michael Elovskikh]
- Added :meth:`Image.transform() <wand.image.Image.transform>` method
  which is a convenience method accepting geometry strings to perform
  cropping and resizing.
  [:issue:`50` by Mitch Lindgren]
- Added :attr:`Image.units <wand.image.Image.units>` property.
  [:issue:`45` by Piotr Florczyk]
- Now :meth:`Image.resize() <wand.image.Image.resize>` method raises
  a proper error when it fails for any reason.
  [:issue:`41` by Piotr Florczyk]
- Added :attr:`Image.type <wand.image.Image.type>` property.
  [:issue:`33` by Yauhen Yakimovich, :issue:`42` by Piotr Florczyk]

__ http://olivier-freebsd-ports.googlecode.com/hg-history/efb852a5572/graphics/py-wand/files/patch-wand_api.py


Version 0.2.1
-------------

Released on August 19, 2012.  Beta version.

- Added :meth:`Image.trim() <wand.image.Image.trim>` method.
  [:issue:`26` by Jökull Sólberg Auðunsson]

- Added :attr:`Image.depth <wand.image.Image.depth>` property.
  [:issue:`31` by Piotr Florczyk]

- Now :class:`~wand.image.Image` can take an optional ``format`` hint.
  [:issue:`32` by Michael Elovskikh]

- Added :attr:`Image.alpha_channel <wand.image.Image.alpha_channel>`
  property.  [:issue:`35` by Piotr Florczyk]

- The default value of :meth:`Image.resize() <wand.image.Image.resize>`'s
  ``filter`` option has changed from ``'triangle'`` to ``'undefined'``.
  [:issue:`37` by Piotr Florczyk]

- Added version data of the linked ImageMagick library into :mod:`wand.version`
  module:

  - :const:`~wand.version.MAGICK_VERSION` (:c:func:`GetMagickVersion`)
  - :const:`~wand.version.MAGICK_VERSION_INFO` (:c:func:`GetMagickVersion`)
  - :const:`~wand.version.MAGICK_VERSION_NUMBER` (:c:func:`GetMagickVersion`)
  - :const:`~wand.version.MAGICK_RELEASE_DATE` (:c:func:`GetMagickReleaseDate`)
  - :const:`~wand.version.MAGICK_RELEASE_DATE_STRING`
    (:c:func:`GetMagickReleaseDate`)


Version 0.2.0
-------------

Released on June 20, 2012.  Alpha version.

- Added :meth:`Image.transparentize() <wand.image.Image.transparentize>` method.
  [:issue:`19` by Jeremy Axmacher]
- Added :meth:`Image.composite() <wand.image.Image.composite>` method.
  [:issue:`19` by Jeremy Axmacher]
- Added :meth:`Image.watermark() <wand.image.Image.watermark>` method.
  [:issue:`19` by Jeremy Axmacher]
- Added :attr:`Image.quantum_range <wand.image.Image.quantum_range>` property.
  [:issue:`19` by Jeremy Axmacher]
- Added :meth:`Image.reset_coords() <wand.image.Image.reset_coords>` method
  and ``reset_coords`` option to :meth:`Image.rotate()
  <wand.image.Image.rotate>` method. [:issue:`20` by Juan Pablo Scaletti]
- Added :meth:`Image.strip() <wand.image.Image.strip>` method.
  [:issue:`23` by Dmitry Vukolov]
- Added :attr:`Image.compression_quality <wand.image.Image.compression_quality>`
  property.  [:issue:`23` by Dmitry Vukolov]
- Now the current version can be found from the command line interface:
  ``python -m wand.version``.


Version 0.1.10
--------------

Released on May 8, 2012.  Still alpha version.

- So many Windows compatibility issues are fixed. [:issue:`14` by John Simon]
- Added :data:`wand.api.libmagick`.
- Fixed a bug that raises :exc:`~exceptions.AttributeError` when it's trying
  to warn.  [:issue:`16` by Tim Dettrick]
- Now it throws :exc:`~exceptions.ImportError` instead of
  :exc:`~exceptions.AttributeError` when the shared library fails
  to load.  [:issue:`17` by Kieran Spear]
- Fixed the example usage on index page of the documentation.
  [:issue:`18` by Jeremy Axmacher]


Version 0.1.9
-------------

Released on December 23, 2011. Still alpha version.

- Now :const:`wand.version.VERSION_INFO` becomes :class:`tuple` and
  :const:`wand.version.VERSION` becomes a string.
- Added :attr:`Image.background_color <wand.image.Image.background_color>`
  property.
- Added ``==`` operator for :class:`~wand.image.Image` type.
- Added :func:`hash()` support of :class:`~wand.image.Image` type.
- Added :attr:`Image.signature <wand.image.Image.signature>` property.
- Added :mod:`wand.display` module.
- Changed the theme of Sphinx documentation.
- Changed the start example of the documentation.

Version 0.1.8
-------------

Released on December 2, 2011. Still alpha version.

- Wrote some guide documentations: :doc:`guide/read`, :doc:`guide/write` and
  :doc:`guide/resizecrop`.
- Added :meth:`Image.rotate() <wand.image.Image.rotate>` method for in-place
  rotation.
- Made :meth:`Image.crop() <wand.image.Image.crop>` to raise proper
  :exc:`ValueError` instead of :exc:`IndexError` for invalid width/height
  arguments.
- Changed the type of :meth:`Image.resize() <wand.image.Image.resize()>`
  method's ``blur`` parameter from :class:`numbers.Rational` to
  :class:`numbers.Real`.
- Fixed a bug of raising :exc:`~exceptions.ValueError` when invalid ``filter``
  has passed to :meth:`Image.resize() <wand.image.Image.resize>` method.

Version 0.1.7
-------------

Released on November 10, 2011. Still alpha version.

- Added :attr:`Image.mimetype <wand.image.Image.mimetype>` property.
- Added :meth:`Image.crop() <wand.image.Image.crop>` method for in-place
  crop.

Version 0.1.6
-------------

Released on October 31, 2011. Still alpha version.

- Removed a side effect of :class:`Image.make_blob()
  <wand.image.Image.make_blob>` method that changes the image format silently.
- Added :attr:`Image.format <wand.image.Image.format>` property.
- Added :meth:`Image.convert() <wand.image.Image.convert>` method.
- Fixed a bug about Python 2.6 compatibility.
- Use the internal representation of :c:type:`PixelWand` instead of
  the string representaion for :class:`~wand.color.Color` type.

Version 0.1.5
-------------

Released on October 28, 2011. Slightly mature alpha version.

- Now :class:`~wand.image.Image` can read Python file objects by ``file``
  keyword argument.
- Now :class:`Image.save() <wand.image.Image.save>` method can write into
  Python file objects by ``file`` keyword argument.
- :class:`Image.make_blob() <wand.image.Image.make_blob>`'s ``format``
  argument becomes omittable.

Version 0.1.4
-------------

Released on October 27, 2011. Hotfix of the malformed Python package.

Version 0.1.3
-------------

Released on October 27, 2011. Slightly mature alpha version.

- Pixel getter for :class:`~wand.image.Image`.
- Row getter for :class:`~wand.image.Image`.
- Mac compatibility.
- Windows compatibility.
- 64-bit processor compatibility.

Version 0.1.2
-------------

Released on October 16, 2011. Still alpha version.

- :class:`~wand.image.Image` implements iterable interface.
- Added :mod:`wand.color` module.
- Added the abstract base class of all Wand resource objects:
  :class:`wand.resource.Resource`.
- :class:`~wand.image.Image` implements slicing.
- Cropping :class:`~wand.image.Image` using its slicing operator.

Version 0.1.1
-------------

Released on October 4, 2011. Still alpha version.

- Now it handles errors and warnings properly and in natural way of Python.
- Added :meth:`Image.make_blob() <wand.image.Image.make_blob>` method.
- Added ``blob`` parameter into :class:`~wand.image.Image` constructor.
- Added :meth:`Image.resize() <wand.image.Image.resize>` method.
- Added :meth:`Image.save() <wand.image.Image.save>` method.
- Added :meth:`Image.clone() <wand.image.Image.clone>` method.
- Drawed `the pretty logo picture <_static/wand.png>`_
  (thanks to `Hyojin Choi <http://me2day.net/crocodile>`_).


Version 0.1.0
-------------

Released on October 1, 2011. Very alpha version.

