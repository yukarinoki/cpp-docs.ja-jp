---
title: no_injected_text (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9289c1b8f28b90dd5a3a4a437d3e2a5870e8468
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791799"
---
# <a name="noinjectedtext"></a>no_injected_text

コンパイラがコードの属性を使用した結果として挿入するを防ぎます。

## <a name="syntax"></a>構文

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>パラメーター

*ブール値*<br/>
(省略可能)**true** 、挿入されたコードが必要ない場合**false**挿入するコードを許可します。 **true**既定値です。

## <a name="remarks"></a>Remarks

最も一般的な用途、 **no_injected_text** C++ 属性は、 [/Fx](../../build/reference/fx-merge-injected-code.md)コンパイラ オプションは、挿入、 **no_injected_text**属性が .mrg ファイルにします。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)  