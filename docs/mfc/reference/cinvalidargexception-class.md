---
title: CInvalidArgException クラス
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: d2df9b482fe95ad0a13a85a51037a4cbbc28d057
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260193"
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
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|コンストラクターです。|

## <a name="remarks"></a>Remarks

A`CInvalidArgException`オブジェクトは無効な引数の例外条件を表します。

例外処理の詳細については、、 [CException クラス](../../mfc/reference/cexception-class.md)トピックと[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="cinvalidargexception"></a>  CInvalidArgException::CInvalidArgException

コンストラクターです。

```
CInvalidArgException();
```

### <a name="remarks"></a>Remarks

このコンス トラクターを直接使用しないでください。グローバル関数を呼び出す**AfxThrowInvalidArgException**します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException クラス](../../mfc/reference/csimpleexception-class.md)
