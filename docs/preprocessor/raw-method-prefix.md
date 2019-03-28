---
title: raw_method_prefix
ms.date: 03/27/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: c3015cf8b51646d25fd8f36a7336c63dc8fe492b
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565598"
---
# <a name="rawmethodprefix"></a>raw_method_prefix

**C++ 固有の仕様**

名前の衝突を避けるために異なるプレフィックスを指定します。

## <a name="syntax"></a>構文

```
raw_method_prefix("Prefix")
```

### <a name="parameters"></a>パラメーター

*Prefix*<br/>
使用されるプレフィックス。

## <a name="remarks"></a>Remarks

低レベルのプロパティとメソッドが既定のプレフィックスを持つという名前のメンバー関数によって公開されている**raw _** 高レベルのエラー処理メンバー関数の名前の競合を回避するためにします。

> [!NOTE]
> 効果、 **raw_method_prefix**の存在によって属性は変更されません、 [raw_interfaces_only](raw-interfaces-only.md)属性。 **Raw_method_prefix**より優先されます`raw_interfaces_only`でプレフィックスを指定します。 両方の属性が同じで使用されている場合`#import`ステートメントでは後で指定されたプレフィックス、 **raw_method_prefix**属性を使用します。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)