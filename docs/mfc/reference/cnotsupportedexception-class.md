---
title: クラスをサポートしていません。
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: b859b939baef018e69b245e597eea90e608253ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363194"
---
# <a name="cnotsupportedexception-class"></a>クラスをサポートしていません。

サポートされていない機能を要求した結果として起こる例外を表します。

## <a name="syntax"></a>構文

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をサポートしていない例外::CNotSupported 例外](#cnotsupportedexception)|`CNotSupportedException` オブジェクトを構築します。|

## <a name="remarks"></a>解説

これ以上の資格は必要ありません。

の使用方法`CNotSupportedException`の詳細については、「[例外処理 (MFC) 」](../../mfc/exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cnotsupportedexceptioncnotsupportedexception"></a><a name="cnotsupportedexception"></a>をサポートしていない例外::CNotSupported 例外

`CNotSupportedException` オブジェクトを構築します。

```
CNotSupportedException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数[AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)を呼び出してください。 例外処理の詳細については[、「MFC での例外処理」を](../exception-handling-in-mfc.md)参照してください。

## <a name="see-also"></a>関連項目

[クラスの例外](cexception-class.md)<br/>
[階層グラフ](../hierarchy-chart.md)
