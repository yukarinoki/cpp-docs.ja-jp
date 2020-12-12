---
description: '詳細については、「_com_error:: Error」を参照してください。'
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 25dd78caeada9e7606bc26f241126b0d0f510f4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318196"
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

オブジェクト内のカプセル化された HRESULT 項目を取得し `_com_error` ます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
