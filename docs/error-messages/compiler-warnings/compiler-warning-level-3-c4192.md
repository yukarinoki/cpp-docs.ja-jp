---
description: '詳細情報: コンパイラの警告 (レベル 3) C4192'
title: コンパイラの警告 (レベル 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 8cfebf1845c578723bab5622e18699c0282d4c4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344225"
---
# <a name="compiler-warning-level-3-c4192"></a>コンパイラの警告 (レベル 3) C4192

タイプライブラリ ' library ' のインポート中に ' name ' を自動的に除外します

ライブラリには、 `#import` Win32 システムヘッダーでも定義されている *名前* の項目が含まれています。 タイプライブラリの制限のため、 **IUnknown** や GUID などの名前は、多くの場合、タイプライブラリで定義され、システムヘッダーから定義が複製されます。 `#import` は、これらの項目を検出し、それを tlh および tli ヘッダーファイルに組み込むことを拒否します。

この動作をオーバーライドするには、 `#import` [no_auto_exclude](../../preprocessor/no-auto-exclude.md) 属性を使用して [() を含め](../../preprocessor/include-parens.md)ます。
