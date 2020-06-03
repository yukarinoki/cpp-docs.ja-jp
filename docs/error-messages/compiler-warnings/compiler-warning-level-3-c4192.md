---
title: コンパイラの警告 (レベル 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 38b346e0a90729bda431b9cb578a03806be1ea4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198979"
---
# <a name="compiler-warning-level-3-c4192"></a>コンパイラの警告 (レベル 3) C4192

タイプライブラリ ' library ' のインポート中に ' name ' を自動的に除外します

`#import` ライブラリには、Win32 システムヘッダーでも定義されている*名前*の項目が含まれています。 タイプライブラリの制限のため、 **IUnknown**や GUID などの名前は、多くの場合、タイプライブラリで定義され、システムヘッダーから定義が複製されます。 これらの項目は `#import` によって検出され、それを tlh および tli ヘッダーファイルに組み込むことを拒否します。

この動作をオーバーライドするには、`#import` 属性[no_auto_exclude](../../preprocessor/no-auto-exclude.md)と[include ()](../../preprocessor/include-parens.md)を使用します。
