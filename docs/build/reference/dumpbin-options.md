---
title: DUMPBIN オプション
ms.date: 10/24/2019
f1_keywords:
- dumpbin
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 81c66f1971294531a2904a0b681819476bcc1eb2
ms.sourcegitcommit: 6ed1bc5b26dc60a780c1fc5f2f19d57ba1dc47d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73144559"
---
# <a name="dumpbin-options"></a>DUMPBIN オプション

オプションは、ダッシュ (`-`) またはスラッシュ (`/`) のいずれかのオプション*指定子*で構成され、その後にオプションの名前が続きます。 オプション名を省略することはできません。 一部のオプションは、コロン (`:`) の後に指定された引数を受け取ります。 1 つのオプションの指定には、スペースやタブは挿入できません。 複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。 オプション名とそのキーワードまたはファイル名の引数では、大文字と小文字が区別されません。 ほとんどのオプションはすべてのバイナリファイルに適用されますが、特定の種類のファイルにのみ適用されます。 特に指定されていない限り、DUMPBIN は標準出力に情報を出力します。 [/Out](out-dumpbin.md)オプションを使用して、出力をファイルに送信します。

## <a name="options-list"></a>オプションの一覧

DUMPBIN には、次のオプションがあります。

- [/ALL](all.md)

- [/ARCHIVEMEMBERS](archivemembers.md)

- [/CLRHEADER](clrheader.md)

- [/DEPENDENTS](dependents.md)

- [/DIRECTIVES](directives.md)

- [/Disasm\[: {BYTES\|NOBYTES}\]](disasm.md)

- [/ERRORREPORT: {NONE |PROMPT |QUEUE |メッセージ](errorreport-dumpbin-exe.md)

- [/EXPORTS](dash-exports.md)

- [/FPO](fpo.md)

- [/HEADERS](headers.md)

- [/IMPORTS\[: ファイル名\]](imports-dumpbin.md)

- [/LINENUMBERS](linenumbers.md)

- [/LINKERMEMBER\[: {1 | 2}\]](linkermember.md)

- [/LOADCONFIG](loadconfig.md)

- [/NOPDB](nopdb.md)

- [/OUT: ファイル名](out-dumpbin.md)

- [/PDATA](pdata.md)

- [/PDBPATH\[: VERBOSE\]](pdbpath.md)

- [/Rangee: vaMin\[、vaMax\]](range.md)

- [/RAWDATA\[: {NONE\|1\|2\|4\|8}\[、#\]\]](rawdata.md)

- [/RELOCATIONS](relocations.md)

- [/SECTION: 名前](section-dumpbin.md)

- [/SUMMARY](summary.md)

- [/SYMBOLS](symbols.md)

- [/TLS](tls.md)

コマンドラインで DUMPBIN でサポートされているオプションを一覧表示するには、/? を使用し**ます。** オプション.

## <a name="see-also"></a>関連項目

[その他の MSVC ビルドツール](c-cpp-build-tools.md)\
[DUMPBIN コマンドライン](dumpbin-command-line.md)\
[DUMPBIN リファレンス](dumpbin-reference.md)
