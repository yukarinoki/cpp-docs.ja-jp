---
title: 致命的なエラー C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: 6ed70a81c4ae2028d09b694f325f83454e99a587
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203100"
---
# <a name="fatal-error-c1382"></a>致命的なエラー C1382

' obj ' が生成された後に PCH ファイル ' file ' が再構築されました。 このオブジェクトをリビルドしてください。

[/Ltcg](../../build/reference/ltcg-link-time-code-generation.md)を使用すると、コンパイラはそれを指す CIL より新しい .pch ファイルを検出しました。 CIL ファイル内の情報が古くなっています。 オブジェクトを再構築します。

C1382 は、 **/yc**を使用してコンパイルした場合にも発生しますが、複数のソースコードファイルをコンパイラに渡すこともできます。  解決するには、複数のソースコードファイルをコンパイラに渡すときに **/yc**を使用しないでください。  詳細については、「 [/yc (プリコンパイル済みヘッダーファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)」を参照してください。
