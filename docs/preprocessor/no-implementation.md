---
description: 詳細については、「no_implementation import 属性」を参照してください。
title: no_implementation インポート属性
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 0cfd51b344847d2e5658fd4e4ec1a9f30db51fe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333326"
---
# <a name="no_implementation-import-attribute"></a>no_implementation インポート属性

**C++ 固有の仕様**

`.tli`ラッパーメンバー関数の実装を含むヘッダーの生成を抑制します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **no_implementation**

## <a name="remarks"></a>解説

この属性が指定されている場合は、ヘッダー `.tlh` ファイルをインクルードするステートメントを使用せずに、タイプライブラリ項目を公開する宣言を含むヘッダーが生成され `#include` `.tli` ます。

この属性は、 [implementation_only](../preprocessor/implementation-only.md)と組み合わせて使用されます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
