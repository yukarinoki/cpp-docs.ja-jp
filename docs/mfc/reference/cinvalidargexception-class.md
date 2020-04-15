---
title: クラスを無効にします。
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: b28b6e84043b85a8117694a67ff5fff13e7c786b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372375"
---
# <a name="cinvalidargexception-class"></a>クラスを無効にします。

このクラスは、無効な引数の例外状態を表します。

## <a name="syntax"></a>構文

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[例外を返します。](#cinvalidargexception)|コンストラクターです。|

## <a name="remarks"></a>解説

オブジェクト`CInvalidArgException`が無効な引数例外条件を表しています。

例外処理の詳細については[、「CException クラス](../../mfc/reference/cexception-class.md)」および[「例外処理 (MFC)」](../../mfc/exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a>例外を返します。

コンストラクターです。

```
CInvalidArgException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用しないでください。グローバル関数を呼び出**します**。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/csimpleexception-class.md)
