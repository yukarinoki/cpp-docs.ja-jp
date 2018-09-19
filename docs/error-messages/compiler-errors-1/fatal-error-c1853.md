---
title: 致命的なエラー C1853 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 016e5bbf064643ddff0f63c5e16a967ed914f3e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044952"
---
# <a name="fatal-error-c1853"></a>致命的なエラー C1853

> '*filename*' プリコンパイル済みヘッダー ファイルは、コンパイラの以前のバージョンから、またはプリコンパイル済みヘッダーは C++ および C から (またはその逆) に使用されます

以下の原因が考えられます。

- プリコンパイル済みヘッダーは、旧バージョンのコンパイラでコンパイルされました。 現在のコンパイラでヘッダーを再コンパイルしてください。

- プリコンパイル済みヘッダーは C++ および C で使用するためのヘッダーを再コンパイルのいずれかを指定することによって C から使用している、 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)コンパイラ オプション、またはソース ファイルのサフィックスの"c"に変更します。 詳細については、次を参照してください。[コードをプリコンパイルする 2 つの選択肢](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code)します。