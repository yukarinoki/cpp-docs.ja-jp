---
title: raw_native_types
ms.date: 11/04/2016
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 32b77905ef7025334e5101e76864da9a15c50cf6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024969"
---
# <a name="rawnativetypes"></a>raw_native_types
**C++ 固有の仕様**

高レベルのラッパー関数の COM サポート クラスの使用を無効にし、代わりに低レベルのデータ型の使用を強制します。

## <a name="syntax"></a>構文

```
raw_native_types
```

## <a name="remarks"></a>Remarks

既定では、高レベルのエラー処理メソッドは、COM サポート クラスを使用して[_bstr_t](../cpp/bstr-t-class.md)と[_variant_t](../cpp/variant-t-class.md)の代わりに、`BSTR`と`VARIANT`データ型および生の COM インターフェイス ポインター。 これらのクラスは、これらのデータ型のメモリ ストレージの割り当てと解放の詳細情報をカプセル化し、型キャストと変換演算を大幅に簡略化します。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)