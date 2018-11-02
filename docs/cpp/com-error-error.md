---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 606f553060e71ece18b3d48159ec40133be28965
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465469"
---
# <a name="comerrorerror"></a>_com_error::Error

**Microsoft 固有の仕様**

コンス トラクターに渡された HRESULT を取得します。

## <a name="syntax"></a>構文

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>戻り値

生の HRESULT 項目は、コンス トラクターに渡されます。

## <a name="remarks"></a>Remarks

カプセル化された HRESULT 項目を取得、`_com_error`オブジェクト。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)