---
title: 致命的なエラー C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 30cf003cc81cb27f7c68b7f0a38529e2d9c88ef5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677826"
---
# <a name="fatal-error-c1853"></a>致命的なエラー C1853

> '*filename*' プリコンパイル済みヘッダー ファイルは、コンパイラの以前のバージョンから、またはプリコンパイル済みヘッダーは C++ および C から (またはその逆) に使用されます

以下の原因が考えられます。

- プリコンパイル済みヘッダーは、旧バージョンのコンパイラでコンパイルされました。 現在のコンパイラでヘッダーを再コンパイルしてください。

- プリコンパイル済みヘッダーは C++ および C で使用するためのヘッダーを再コンパイルのいずれかを指定することによって C から使用している、 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション、またはソース ファイルのサフィックスの"c"に変更します。 詳細については、次を参照してください。[コードをプリコンパイルする 2 つの選択肢](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code)します。