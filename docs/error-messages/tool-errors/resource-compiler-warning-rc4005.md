---
title: リソース コンパイラの警告 RC4005 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 589fd008b3927887a8144b2fc63d2cbbde2af913
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028520"
---
# <a name="resource-compiler-warning-rc4005"></a>リソース コンパイラの警告 RC4005

'identifier': 再定義はマクロ

識別子は、2 回定義されます。 コンパイラは、2 つ目のマクロ定義を使用します。

この警告は、コマンドラインで、コードで、マクロの定義によって発生すること、`#define`ディレクティブ。 それも可能性がありますインクルード ファイルからインポートされたマクロで。

警告を排除するために、定義の 1 つを削除またはのいずれかを使用して、`#undef`ディレクティブを 2 番目の定義。