---
description: 詳細については、「raw_interfaces_only import 属性」を参照してください。
title: raw_interfaces_only インポート属性
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: f043bef5cde0454ce9f08f45efb0417aa7fdbb2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142741"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only インポート属性

**C++ 固有の仕様**

エラー処理ラッパー関数、およびそれらのラッパー関数を使用する [プロパティ](../cpp/property-cpp.md) 宣言を生成しません。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **raw_interfaces_only**

## <a name="remarks"></a>解説

また、 **raw_interfaces_only** 属性を指定すると、非プロパティ関数の名前付けに使用される既定のプレフィックスも削除されます。 通常、プレフィックスは `raw_` です。 この属性が指定されている場合、関数名はタイプライブラリから直接取得されます。

この属性を使用することで、タイプ ライブラリの低水準の内容のみを公開できます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
