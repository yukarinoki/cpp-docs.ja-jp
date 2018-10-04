---
title: usesgetlasterror (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 501f6b1801ace9f6002cca5d3559dfcb01e994f5
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791306"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

呼び出し元に通知する関数を呼び出すときにエラーがある場合、呼び出し元ことができますし`GetLastError`エラー コードを取得します。

## <a name="syntax"></a>構文

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Remarks

**Usesgetlasterror** C++ 属性と同じ機能を持つ、 [usesgetlasterror](/windows/desktop/Midl/usesgetlasterror) MIDL 属性。

## <a name="example"></a>例

参照してください、 [idl_module](idl-module.md)を使用する方法のサンプルについては、例**usesgetlasterror**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**モジュール**属性|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)  