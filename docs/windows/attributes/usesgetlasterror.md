---
title: usesgetlasterror (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: 9f050bbf69edf1ab8327a283299cb5e687ce5380
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407069"
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

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**モジュール**属性|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)