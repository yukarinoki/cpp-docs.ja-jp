---
description: '詳細情報: CInvalidArgException クラス'
title: CInvalidArgException クラス
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: f68642747a81d1c45a8246f4f25abfb8b79c81d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202796"
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException クラス

このクラスは、無効な引数の例外状態を表します。

## <a name="syntax"></a>構文

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CInvalidArgException:: CInvalidArgException](#cinvalidargexception)|コンストラクターです。|

## <a name="remarks"></a>解説

`CInvalidArgException`オブジェクトが無効な引数の例外条件を表しています。

例外処理の詳細については、「 [CException クラス](../../mfc/reference/cexception-class.md) 」トピックと「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a> CInvalidArgException:: CInvalidArgException

コンストラクターです。

```
CInvalidArgException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用しないでください。グローバル関数 **AfxThrowInvalidArgException** を呼び出します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException クラス](../../mfc/reference/csimpleexception-class.md)
