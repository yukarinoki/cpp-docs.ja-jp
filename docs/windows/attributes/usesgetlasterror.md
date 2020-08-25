---
title: 方法 getlasterror (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: e3d3c292554350d85296971a9bd3620909ef47c7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831633"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

この関数を呼び出したときにエラーが発生した場合に、呼び出し元がを呼び出してエラーコードを取得できることを呼び出し元に通知し `GetLastError` ます。

## <a name="syntax"></a>構文

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>解説

Has **getlasterror** C++ 属性に [は、すべて](/windows/win32/Midl/usesgetlasterror) の機能と同じ機能があります。

## <a name="example"></a>例

使用方法の例については、 [idl_module](idl-module.md)の例を**参照してください。**

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**module** 属性|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)
