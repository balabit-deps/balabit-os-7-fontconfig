# -*- encoding: utf-8 -*-
#
# Copyright © 2003  Keith Packard
#
# Permission to use, copy, modify, distribute, and sell this software and its
# documentation for any purpose is hereby granted without fee, provided that
# the above copyright notice appear in all copies and that both that
# copyright notice and this permission notice appear in supporting
# documentation, and that the name of the author(s) not be used in
# advertising or publicity pertaining to distribution of the software without
# specific, written prior permission.  The authors make no
# representations about the suitability of this software for any purpose.  It
# is provided "as is" without express or implied warranty.
#
# THE AUTHOR(S) DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
# INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS, IN NO
# EVENT SHALL THE AUTHOR(S) BE LIABLE FOR ANY SPECIAL, INDIRECT OR
# CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE,
# DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER
# TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
# PERFORMANCE OF THIS SOFTWARE.

NULL =
BLANKSPY = fc-blanks.py
BLANKS_H = fcblanks.h
TMPL = fcblanks.tmpl.h
noinst_SCRIPTS = $(BLANKSPY)
noinst_HEADERS = $(BLANKS_H)

$(BLANKS_H): $(TMPL) $(BLANKSPY)
if HAVE_PYTHON
	$(AM_V_GEN) $(PYTHON) $(srcdir)/$(BLANKSPY) < $< > $(BLANKS_H).tmp && \
	mv $(BLANKS_H).tmp $(BLANKS_H) || ($(RM) $(BLANKS_H).tmp && false)
else
	@echo "No python installed. please install python to build $(BLANKS_H)."
	@false
endif

EXTRA_DIST = 		\
	$(BLANKSPY)	\
	$(BLANKS_H)	\
	$(TMPL)		\
	$(NULL)
DISTCLEANFILES = $(BLANKS_H)

-include $(top_srcdir)/git.mk
