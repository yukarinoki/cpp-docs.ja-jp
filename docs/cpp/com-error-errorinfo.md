---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: cedb9ccadc63166c43d980333d93a195254700d8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180707"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft 固有の仕様**

コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。

## <a name="syntax"></a>構文

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>戻り値

コンストラクターに渡された未処理の `IErrorInfo` 項目。

## <a name="remarks"></a>解説

`_com_error` オブジェクト内のカプセル化された `IErrorInfo` 項目を取得します。 `IErrorInfo` 項目が記録されていない場合は NULL を取得します。 呼び出し元は、使用が終了したときに、返されたオブジェクトの `Release` を呼び出す必要があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
