---
description: '詳細情報: uuid (C++)'
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c841bb1813769ab70e756fe4edb7fd351c1dbc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116731"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft 固有の仕様**

コンパイラは、属性を使用して、宣言または定義された (完全な COM オブジェクト定義のみ) クラスまたは構造体に GUID をアタッチし **`uuid`** ます。

## <a name="syntax"></a>構文

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>解説

属性は、 **`uuid`** 引数として文字列を受け取ります。 この文字列は、 **{}** 区切り記号の有無に関係なく、通常のレジストリ形式で GUID に名前を付けます。 次に例を示します。

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

この属性は、再宣言で適用できます。 これにより、システムヘッダーは、などのインターフェイスの定義、 `IUnknown` および他のヘッダー (など) の再宣言によって \<comdef.h> GUID を指定できます。

キーワード [__uuidof](../cpp/uuidof-operator.md) を適用して、ユーザー定義型にアタッチされている定数 GUID を取得できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
