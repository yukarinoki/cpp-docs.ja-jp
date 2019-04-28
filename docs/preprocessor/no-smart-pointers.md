---
title: no_smart_pointers
ms.date: 11/04/2016
f1_keywords:
- no_search_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: ed4950b9e90ef968fcf0c42e4f0a9775c58ea7ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326509"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C++ 固有の仕様**

タイプ ライブラリのすべてのインターフェイスに対して、スマート ポインターの作成を抑制します。

## <a name="syntax"></a>構文

```
no_smart_pointers
```

## <a name="remarks"></a>Remarks

既定では、`#import` を使用すると、タイプ ライブラリのすべてのインターフェイスのスマート ポインター宣言を取得できます。 これらのスマート ポインターは型[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)します。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)