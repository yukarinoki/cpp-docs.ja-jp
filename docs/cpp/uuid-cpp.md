---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: 09e40d38382bea0f902fda03d15d24e0cf1a627d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187805"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft 固有の仕様**

コンパイラは、 **uuid**属性を使用して、宣言または定義された (完全な COM オブジェクト定義のみ) クラスまたは構造体に GUID をアタッチします。

## <a name="syntax"></a>構文

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>解説

**Uuid**属性は、引数として文字列を受け取ります。 この文字列は、 **{}** 区切り記号の有無に関係なく、通常のレジストリ形式で GUID に名前を付けます。 次に例を示します。

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

この属性は、再宣言で適用できます。 これにより、システムヘッダーは `IUnknown`などのインターフェイスの定義、およびその他のヘッダー (\<comdef. h > など) の再宣言によって GUID を提供できるようになります。

キーワード[__uuidof](../cpp/uuidof-operator.md)を適用して、ユーザー定義型にアタッチされている定数 GUID を取得できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
