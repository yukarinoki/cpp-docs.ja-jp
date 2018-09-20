---
title: CMemoryException クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 028c74bdc0c937fe59b621b81fb6abb8def63707
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385106"
---
# <a name="cmemoryexception-class"></a>CMemoryException クラス

メモリ不足例外条件を表します。

## <a name="syntax"></a>構文

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMemoryException::CMemoryException](#cmemoryexception)|`CMemoryException` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

さらに認定には、必要なまたはことはありません。 メモリ不足例外のスローによって自動的に**新しい**します。 使用して、独自のメモリ関数を記述する場合`malloc`、後の例ではメモリの例外をスローする責任があります。

詳細については`CMemoryException`、記事をご覧ください[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>要件

**ヘッダー:** afx.h

##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException

`CMemoryException` オブジェクトを構築します。

```
CMemoryException();
```

### <a name="remarks"></a>Remarks

このコンス トラクターを直接使用されませんではなく、グローバル関数を呼び出す[AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)します。 このグローバル関数は、以前に割り当てられたメモリ内の例外オブジェクトを構築するので、メモリ不足の状況で成功ことができます。 例外の処理の詳細については、記事を参照してください。[例外](../exception-handling-in-mfc.md)します。

## <a name="see-also"></a>関連項目

[CException クラス](cexception-class.md)<br/>
[階層図](../hierarchy-chart.md)



