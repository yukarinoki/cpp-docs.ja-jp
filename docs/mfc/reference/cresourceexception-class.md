---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: 557bfe1cc41c3dda65bd95d7d687820c0b9862b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368329"
---
# <a name="cresourceexception-class"></a>クラス

Windows が要求されたリソースを見つけられないか、割り当てられないときに生成されます。

## <a name="syntax"></a>構文

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の処理を行います。](#cresourceexception)|`CResourceException` オブジェクトを構築します。|

## <a name="remarks"></a>解説

これ以上の資格は必要ありません。

の使用方法`CResourceException`の詳細については、「[例外処理 (MFC) 」](../../mfc/exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a>次の処理を行います。

`CResourceException` オブジェクトを構築します。

```
CResourceException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)を呼び出してください。 例外の詳細については[、「MFC での例外処理」を](../exception-handling-in-mfc.md)参照してください。

## <a name="see-also"></a>関連項目

[クラスの例外](cexception-class.md)<br/>
[階層グラフ](../hierarchy-chart.md)
