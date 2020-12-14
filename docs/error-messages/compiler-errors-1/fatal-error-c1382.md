---
description: '詳細情報: 致命的なエラー C1382'
title: 致命的なエラー C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: fd2b9f48030d558a880a787114848dd0551b68ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276518"
---
# <a name="fatal-error-c1382"></a>致命的なエラー C1382

PCH ファイル 'file' は、'obj' が生成された後にリビルドされています。 このオブジェクトをリビルドしてください。

[/Ltcg](../../build/reference/ltcg-link-time-code-generation.md)を使用すると、コンパイラはそれを指す CIL より新しい .pch ファイルを検出しました。 CIL ファイル内の情報が古くなっています。 オブジェクトを再構築します。

C1382 は、 **/yc** を使用してコンパイルした場合にも発生しますが、複数のソースコードファイルをコンパイラに渡すこともできます。  解決するには、複数のソースコードファイルをコンパイラに渡すときに **/yc** を使用しないでください。  詳細については、「 [/yc (プリコンパイル済みヘッダーファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)」を参照してください。
