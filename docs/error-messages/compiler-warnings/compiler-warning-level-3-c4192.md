---
title: コンパイラの警告 (レベル 3) C4192 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 671a8c83dcadcaa89372e53b6c3d677c5810b4a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114411"
---
# <a name="compiler-warning-level-3-c4192"></a>コンパイラの警告 (レベル 3) C4192

タイプ ライブラリ 'library' のインポート中に 'name' を自動的に除外

A`#import`ライブラリにはアイテムが含まれています*名前*、つまり、Win32 システム ヘッダーでも定義されています。 などのタイプ ライブラリの制限により名**IUnknown** GUID は多くの場合で定義されているタイプ ライブラリでは、システム ヘッダーの定義を複製します。 `#import` これらの項目を検出し、.tlh と .tli ヘッダー ファイルに組み込むことを拒否します。

この動作をオーバーライドするには使用`#import`属性[no_auto_exclude](../../preprocessor/no-auto-exclude.md)と[include()](../../preprocessor/include-parens.md)します。