---
title: 致命的なエラー C1382 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a5a6ce312c5ef886ef25e8de46e6d3376eded2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030655"
---
# <a name="fatal-error-c1382"></a>致命的なエラー C1382

PCH ファイル 'file' が、'obj' が生成されてから再構築されました。 このオブジェクトをリビルドしてください。

使用する場合[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)、それを指して CIL .obj ファイルより新しい .pch ファイルが検出されました。 CIL .obj ファイル内の情報が古くなっています。 オブジェクトを再構築します。

使用してコンパイルする場合にも C1382 **/Yc**に渡すことも複数のソース コード ファイル、コンパイラが。  を解決するを使用しないで **/Yc**複数のソース コード ファイルをコンパイラに渡すときにします。  詳細については、次を参照してください。 [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)します。