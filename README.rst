Aldhikr-theme can be installed as a Tutor plugin::

    tutor local stop
    cd $(tutor config printroot)/env/build/openedx/requirements
    git clone https://github.com/blend-ed/tutor-aldhikr-theme
    pip install -e ./tutor-aldhikr-theme
    tutor plugins enable aldhikr-theme
    tutor config save

Rebuild the Openedx docker image::

    tutor images build openedx

Restart your platform::

    tutor local start -d

You will then have to enable the "aldhikr-theme" theme, as per the `Tutor documentation <https://docs.tutor.overhang.io/local.html#setting-a-new-theme>`__::

    tutor local do settheme aldhikr-theme

Configuration
-------------

- ``ALDHIKR_WELCOME_MESSAGE`` (default: "Learning in all dimensions")
- ``ALDHIKR_PRIMARY_COLOR`` (default: "#009cc7")
- ``ALDHIKR_FOOTER_NAV_LINKS`` (default: ``[{"title": "About", "url": "/about"}, {"title": "Contact", "url": "/contact"}]``)
- ``ALDHIKR_FOOTER_LEGAL_LINKS`` (default: ``[{"title": "Terms of service", "url": "/tos"}, {"title": "ALDHIKR theme for Open edX", "url": "https://github.com/overhangio/tutor-ALDHIKR"}]``)

The ``ALDHIKR_*`` settings listed above may be modified by running ``tutor config save --set ALDHIKR_...=...``. For instance, to remove all links from the footer, run::

    tutor config save --set "ALDHIKR_FOOTER_NAV_LINKS=[]" --set "ALDHIKR_FOOTER_LEGAL_LINKS=[]"