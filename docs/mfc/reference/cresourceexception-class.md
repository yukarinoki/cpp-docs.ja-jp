---
title: CResourceException クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs:
- C++
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e1fea7db1ef79eed2bc2678bd1e9283c71bb161
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071863"
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
|[CResourceException::CResourceException](#cresourceexception)|`CResourceException` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

さらに認定には、必要なまたはことはありません。

使用しての詳細については`CResourceException`、記事をご覧ください[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cresourceexception"></a>  CResourceException::CResourceException

`CResourceException` オブジェクトを構築します。

```
CResourceException();
```

### <a name="remarks"></a>Remarks

このコンス トラクターを直接使用されませんではなく、グローバル関数を呼び出す[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)します。 例外の詳細については、記事を参照してください。[例外処理 (mfc)](../exception-handling-in-mfc.md)します。

## <a name="see-also"></a>関連項目

[CException クラス](cexception-class.md)<br/>
[階層図](../hierarchy-chart.md)

