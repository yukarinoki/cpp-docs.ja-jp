---
description: '詳細情報: CResourceException クラス'
title: CResourceException クラス
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: c76635ae2cfa6c55bf54da7e73f6afbb44506fee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264870"
---
# <a name="cresourceexception-class"></a>CResourceException クラス

Windows が要求されたリソースを見つけられないか、割り当てられないときに生成されます。

## <a name="syntax"></a>構文

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CResourceException:: CResourceException](#cresourceexception)|`CResourceException` オブジェクトを構築します。|

## <a name="remarks"></a>解説

これ以上の修飾は必要ありません。

の使用方法の詳細については `CResourceException` 、「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a> CResourceException:: CResourceException

`CResourceException` オブジェクトを構築します。

```
CResourceException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数 [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)を呼び出します。 例外の詳細については、「 [MFC での例外処理](../exception-handling-in-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CException クラス](cexception-class.md)<br/>
[階層図](../hierarchy-chart.md)
