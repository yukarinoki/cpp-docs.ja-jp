---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 375b4227a25ae4c18cfd263eff4c3ec13f1304e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370002"
---
# <a name="cmemoryexception-class"></a>クラス

メモリ不足例外条件を表します。

## <a name="syntax"></a>構文

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::Cメモリ例外](#cmemoryexception)|`CMemoryException` オブジェクトを構築します。|

## <a name="remarks"></a>解説

これ以上の資格は必要ありません。 メモリ例外は、**新しい**. たとえば、 を使用して`malloc`独自のメモリ関数を記述する場合は、メモリ例外をスローする責任があります。

の詳細については、「[例外処理 (MFC) 」](../../mfc/exception-handling-in-mfc.md)を参照してください。 `CMemoryException`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a>::Cメモリ例外

`CMemoryException` オブジェクトを構築します。

```
CMemoryException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数[AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)を呼び出してください。 このグローバル関数は、以前に割り当てられたメモリに例外オブジェクトを構築するため、メモリ不足の状況で成功する可能性があります。 例外処理の詳細については、 の記事の[「例外](../exception-handling-in-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの例外](cexception-class.md)<br/>
[階層グラフ](../hierarchy-chart.md)
