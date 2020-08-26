---
title: CSimpleException クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
ms.openlocfilehash: afd83c1ddd6f68b10c5cc8c47c0e939bbd01b6c2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840714"
---
# <a name="csimpleexception-class"></a>CSimpleException クラス

このクラスは、リソース クリティカルな MFC 例外の基底クラスです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSimpleException::CSimpleException](#csimpleexception)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleException::GetErrorMessage](#geterrormessage)|発生したエラーに関するテキストを提供します。|

## <a name="remarks"></a>解説

`CSimpleException` は、リソースクリティカルな MFC 例外の基本クラスであり、エラーメッセージの所有権と初期化を処理します。 次のクラスは、を `CSimpleException` 基本クラスとして使用します。

|名前|説明|
|-|-|
|[CMemoryException クラス](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|
|[CNotSupportedException クラス](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|
|[CResourceException クラス](../../mfc/reference/cresourceexception-class.md)|Windows リソースが見つからないか、作成できません|
|[CUserException クラス](../../mfc/reference/cuserexception-class.md)|リソースが見つからなかったことを示す例外|
|[CInvalidArgException クラス](../../mfc/reference/cinvalidargexception-class.md)|無効な引数を示す例外|

`CSimpleException`は抽象基本クラスであるため、オブジェクトを直接宣言することはできません `CSimpleException` 。 代わりに、前の表に示すような派生オブジェクトを宣言する必要があります。 独自の派生クラスを宣言する場合は、以前のクラスをモデルとして使用します。

詳細については、「 [CException クラス](../../mfc/reference/cexception-class.md) 」トピックと「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a> CSimpleException::CSimpleException

コンストラクターです。

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*bAutoDelete*<br/>
オブジェクトのメモリが `CSimpleException` ヒープに割り当てられている場合は TRUE を指定します。 これにより、 `CSimpleException` `Delete` 例外を削除するためにメンバー関数が呼び出されたときに、オブジェクトが削除されます。 `CSimpleException`オブジェクトがスタック上にあるか、またはグローバルオブジェクトである場合は、FALSE を指定します。 この場合、メンバー関数が呼び出されても、 `CSimpleException` オブジェクトは削除されません `Delete` 。

### <a name="remarks"></a>解説

通常、このコンストラクターを直接呼び出す必要はありません。 例外をスローする関数は、派生クラスのインスタンスを作成 `CException` してそのコンストラクターを呼び出す必要があります。または、 [AfxThrowFileException](exception-processing.md#afxthrowfileexception)などの MFC スロー関数のいずれかを使用して、定義済みの型をスローする必要があります。

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a> CSimpleException::GetErrorMessage

発生したエラーに関するテキストを提供するには、このメンバー関数を呼び出します。

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszError*<br/>
エラーメッセージを受信するバッファーへのポインター。

*nMaxError*<br/>
バッファーが保持できる最大文字数 (NULL ターミネータを含む)。

*pnHelpContext*<br/>
ヘルプコンテキスト ID を受け取る UINT のアドレス。 NULL の場合、ID は返されません。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は、エラーメッセージテキストを使用できない場合は0になります。

### <a name="remarks"></a>解説

詳細については、「 [CException:: GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)」を参照してください。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CException クラス](../../mfc/reference/cexception-class.md)<br/>
[例外処理](../../mfc/exception-handling-in-mfc.md)
