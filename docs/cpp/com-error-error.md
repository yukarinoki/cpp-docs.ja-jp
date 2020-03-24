---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 8e2c52d10b15822703329dcea18944773f5784ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180759"
---
# <a name="_com_errorerror"></a>_com_error::Error

**Microsoft 固有の仕様**

コンストラクターに渡された HRESULT を取得します。

## <a name="syntax"></a>構文

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>戻り値

コンストラクターに渡された生の HRESULT 項目。

## <a name="remarks"></a>解説

`_com_error` オブジェクト内のカプセル化された HRESULT 項目を取得します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
