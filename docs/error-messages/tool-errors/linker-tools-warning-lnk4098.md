---
title: リンカー ツールの警告 LNK4098 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4098
dev_langs:
- C++
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2068534d51ae1350510a349f875c1977299edb1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019154"
---
# <a name="linker-tools-warning-lnk4098"></a>リンカー ツールの警告 LNK4098

defaultlib 'library' 競合していますが他のライブラリの使用。/NODEFAULTLIB:library を使用します。

互換性のないライブラリとリンクしようとしました。

> [!NOTE]
>  ランタイム ライブラリには、さまざまな種類の混在を回避するためのディレクティブが含まれています。 この警告のさまざまな種類を使用するか、デバッグしようとする場合と非デバッグ バージョンのランタイム ライブラリは、同じプログラム内で表示されます。 たとえば、ファイル (たとえば、シングル スレッドとマルチ スレッドなど) 別の種類を使用して、それらをリンクしようとしています。 もう 1 種類のランタイム ライブラリのいずれかを使用する 1 つのファイルをコンパイルした場合は、この警告が表示されます。 同じランタイム ライブラリを使用するすべてのソース ファイルをコンパイルする必要があります。 参照してください、[ランタイム ライブラリの使用](../../build/reference/md-mt-ld-use-run-time-library.md)(**/MD**、 **/MT**、 **/LD**) 詳細については、コンパイラ オプション。

リンカーを使用する[/VERBOSE:LIB](../../build/reference/verbose-print-progress-messages.md)リンカーが検索するライブラリを決定するスイッチ。 非デバッグ ランタイム ライブラリ、使用の LNK4098 し、シングル スレッドなど、使用する実行可能ファイルを作成する場合に発生した場合、 **/VERBOSE:LIB**オプション、リンカーが検索するライブラリを確認します。 リンカーは、検索したライブラリとして LIBC.lib LIBCMT.lib、MSVCRT.lib、LIBCD.lib、LIBCMTD.lib、やではなく MSVCRTD.lib を印刷する必要があります。 リンカーを使用して、不適切なランタイム ライブラリを無視することがわかります[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)各ライブラリを無視することです。

次の表では、使用するためのランタイム ライブラリによって、どのライブラリを無視するかを示します。

|このライブラリを使用するには|これらのライブラリを無視します。|
|-----------------------------------|----------------------------|
|シングル スレッド (libc.lib)|libcmt.lib、msvcrt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|
|マルチ スレッド (libcmt.lib)|libc.lib、msvcrt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|
|マルチ スレッド DLL (msvcrt.lib) を使用します。|libc.lib、libcmt.lib、libcd.lib、libcmtd.lib、msvcrtd.lib|
|シングル スレッド (libcd.lib) のデバッグします。|libc.lib、libcmt.lib、msvcrt.lib、libcmtd.lib、msvcrtd.lib|
|マルチ スレッド デバッグ (libcmtd.lib)|libc.lib、libcmt.lib、msvcrt.lib、libcd.lib、msvcrtd.lib|
|マルチ スレッド DLL (msvcrtd.lib) を使用したデバッグします。|libc.lib、libcmt.lib、msvcrt.lib、libcd.lib、libcmtd.lib|

たとえば、この警告を受信して、非デバッグ、シングル スレッド バージョンのランタイム ライブラリを使用する実行可能ファイルを作成する場合、は、リンカーで、次のオプションを使用できます。

```
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```