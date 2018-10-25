---
title: CNotSupportedException クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b52151dba90c0cfd0ed834e2ef351838d598eb90
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068803"
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

## <a name="remarks"></a>Remarks

さらに認定には、必要なまたはことはありません。

使用しての詳細については`CNotSupportedException`、記事をご覧ください[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

##  <a name="cnotsupportedexception"></a>  CNotSupportedException::CNotSupportedException

`CNotSupportedException` オブジェクトを構築します。

```
CNotSupportedException();
```

### <a name="remarks"></a>Remarks

このコンス トラクターを直接使用されませんではなく、グローバル関数を呼び出す[AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)します。 例外の処理の詳細については、記事を参照してください。[例外処理 (mfc)](../exception-handling-in-mfc.md)します。

## <a name="see-also"></a>関連項目

[CException クラス](cexception-class.md)<br/>
[階層図](../hierarchy-chart.md)

