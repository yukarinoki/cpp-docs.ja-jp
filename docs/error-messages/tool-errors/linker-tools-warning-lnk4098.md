---
title: リンカー ツールの警告 LNK4098
ms.date: 03/26/2019
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 66cf1a1bc75405ffc9bae8158bfc8682776a8228
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508729"
---
# <a name="linker-tools-warning-lnk4098"></a>リンカー ツールの警告 LNK4098

> defaultlib '*ライブラリ*' と競合していますが他のライブラリの使用は、/NODEFAULTLIB を使用する:*ライブラリ*

互換性のないライブラリとリンクしようとしています。

> [!NOTE]
> ランタイム ライブラリには、さまざまな種類の混在を回避するためのディレクティブが含まれています。 この警告のさまざまな種類を使用するか、デバッグしようとする場合と非デバッグ バージョンのランタイム ライブラリは、同じプログラム内で表示されます。 たとえば、ランタイム ライブラリの 1 つの種類を使用する 1 つのファイルとその他の種類を使用する別のファイルをコンパイルした場合 (たとえば、小売とデバッグ) し、それらをリンクしようとすると、この警告が表示されます。 同じランタイム ライブラリを使用するすべてのソース ファイルをコンパイルする必要があります。 詳細については、次を参照してください。、 [/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)コンパイラ オプション。

リンカーを使用する[/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md)リンカーが検索するライブラリを検索 に切り替える。 など、実行可能ファイルは、マルチ スレッド、非デバッグ ランタイム ライブラリを使用しているときに表示されたリストは LIBCMT.lib、LIBCMTD.lib、MSVCRT.lib、やではなく MSVCRTD.lib を含める必要があります。 リンカーを使用して、不適切なランタイム ライブラリを無視することがわかります[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)各ライブラリを無視することです。

次の表では、使用するためのランタイム ライブラリによって、どのライブラリを無視するかを示します。 コマンドラインで 1 つを使用して **/NODEFAULTLIB**を無視するには、各ライブラリのオプション。 Visual Studio IDE で個別にセミコロンで無視するライブラリ、**特定の既定のライブラリの無視**プロパティ。

| このライブラリを使用するには | これらのライブラリを無視します。 |
|-----------------------------------|----------------------------|
| マルチ スレッド (libcmt.lib) | msvcrt.lib; libcmtd.lib; msvcrtd.lib |
| マルチ スレッド DLL (msvcrt.lib) を使用します。 | libcmt.lib; libcmtd.lib; msvcrtd.lib |
| マルチ スレッド デバッグ (libcmtd.lib) | libcmt.lib; msvcrt.lib; msvcrtd.lib |
| マルチ スレッド DLL (msvcrtd.lib) を使用したデバッグします。 | libcmt.lib; msvcrt.lib; libcmtd.lib |

たとえば、この警告を受信して、実行可能ファイルを作成する場合は、非デバッグ、DLL のバージョンのランタイム ライブラリを使用する、リンカーでは、次のオプションを利用できます。

```cmd
/NODEFAULTLIB:libcmt.lib NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```