---
description: 詳細については、「auto_rename import 属性」を参照してください。
title: auto_rename インポート属性
ms.date: 08/29/2019
f1_keywords:
- auto_rename
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
ms.openlocfilehash: 57406b1f64b3e5e484556ae15600cc30f1e931dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301036"
---
# <a name="auto_rename-import-attribute"></a>auto_rename インポート属性

**C++ 固有の仕様**

潜在的な名前の競合を解決するため、変数名に 2 つのアンダースコア (__) を追加して C++ の予約語の名前を変更します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **auto_rename**

## <a name="remarks"></a>解説

この属性は、変数名として C++ の予約語 (キーワードまたはマクロ) を使用しているタイプ ライブラリをインポートするときに使用します。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
