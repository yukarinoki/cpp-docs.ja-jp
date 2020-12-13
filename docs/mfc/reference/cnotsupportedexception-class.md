---
description: '詳細情報: CNotSupportedException クラス'
title: CNotSupportedException クラス
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: 61bf729753897e1d30c5a12bc371489ba6f2d64f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331475"
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException クラス

サポートされていない機能を要求した結果として起こる例外を表します。

## <a name="syntax"></a>構文

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|`CNotSupportedException` オブジェクトを構築します。|

## <a name="remarks"></a>解説

これ以上の修飾は必要ありません。

の使用方法の詳細については `CNotSupportedException` 、「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cnotsupportedexceptioncnotsupportedexception"></a><a name="cnotsupportedexception"></a> CNotSupportedException::CNotSupportedException

`CNotSupportedException` オブジェクトを構築します。

```
CNotSupportedException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数 [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)を呼び出します。 例外処理の詳細については、「 [MFC での例外処理](../exception-handling-in-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CException クラス](cexception-class.md)<br/>
[階層図](../hierarchy-chart.md)
