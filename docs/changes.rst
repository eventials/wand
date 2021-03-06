Wand Changelog
==============

Version 0.3.0
-------------

To be released.

- Added optional ``color`` parameter to :meth:`Image.border()
  <wand.image.Image.border>` method.
- Added :meth:`Image.border() <wand.image.Image.border>` method.
  [:commit:`2496d37f75d75e9425f95dde07033217dc8afefc` by Jae-Myoung Yu]
- Added ``resolution`` parameter to :meth:`Image.read() <wand.image.Image.read>`
  method and the constructor of :class:`~wand.image.Image`.
  [:issue:`75` by Andrey Antukh]
- Added :meth:`Image.liquid_rescale() <wand.image.Image.liquid_rescale>`
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
- Added :meth:`Image.composite_channel() <wand.image.Image.composite_channel>`
  method.
- Added :meth:`Image.read() <wand.image.read>` method.
  [:issue:`58` by Piotr Florczyk]
- Added :attr:`Image.resolution <wand.image.Image.resolution>` property.
  [:issue:`58` by Piotr Florczyk]
- Added :meth:`Image.blank() <wand.image.blank>` method.
  [:issue:`60` by Piotr Florczyk]
- Fixed several memory leaks.  [:issue:`62` by Mitch Lindgren]
- Added :class:`~wand.image.ImageProperty` mixin class to maintain
  a weak reference to the parent image.
- Ranamed :const:`wand.image.COMPOSITE_OPS` to
  :const:`~wand.image.COMPOSITE_OPERATORS`.
- Now it shows helpful error message when ImageMagick library cannot be
  found.
- Added IPython-specialized formatter.

__ http://en.wikipedia.org/wiki/Seam_carving


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

