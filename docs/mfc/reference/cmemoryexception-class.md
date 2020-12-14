---
description: '詳細情報: CMemoryException クラス'
title: CMemoryException クラス
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 694629d65c8b4cffc351873d5da3d8ed3c34cf8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336654"
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
|[CMemoryException:: CMemoryException](#cmemoryexception)|`CMemoryException` オブジェクトを構築します。|

## <a name="remarks"></a>解説

これ以上の修飾は必要ありません。 メモリ例外は、によって自動的にスローされ **`new`** ます。 たとえば、を使用して独自のメモリ関数を記述する場合 `malloc` は、メモリ例外をスローする必要があります。

の詳細については `CMemoryException` 、「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>要件

**ヘッダー:** afx

## <a name="cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a> CMemoryException:: CMemoryException

`CMemoryException` オブジェクトを構築します。

```
CMemoryException();
```

### <a name="remarks"></a>解説

このコンストラクターを直接使用するのではなく、グローバル関数 [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)を呼び出します。 以前に割り当てられたメモリに例外オブジェクトが構築されるため、このグローバル関数はメモリ不足の状態で成功する可能性があります。 例外処理の詳細については、「 [例外](../exception-handling-in-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CException クラス](cexception-class.md)<br/>
[階層図](../hierarchy-chart.md)
