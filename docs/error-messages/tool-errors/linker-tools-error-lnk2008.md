---
title: リンカ ツール エラー LNK2008
ms.date: 11/04/2016
f1_keywords:
- LNK2008
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
ms.openlocfilehash: c7794d09f7eeb9dceba7098ca7af90ccf2eeccad
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194825"
---
# <a name="linker-tools-error-lnk2008"></a>リンカ ツール エラー LNK2008

Fixup のターゲットが ' symbol_name ' にアラインされていません

リンクは、適切にアラインされていないオブジェクトファイル内の修正ターゲットを見つけました。

このエラーが発生する原因としては、カスタムの secton アラインメント (たとえば、#pragma[パック](../../preprocessor/pack.md))、[アラ](../../cpp/align-cpp.md)イン修飾子、または secton アラインメントを変更するアセンブリ言語コードを使用することが考えられます。

コードで上記のいずれも使用されていない場合は、コンパイラによって発生する可能性があります。
