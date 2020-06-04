---
title: クラス
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
ms.openlocfilehash: eb94ba9e3d26b3cd910f23c3d4abb29d3b8b1cd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318359"
---
# <a name="csimpleexception-class"></a>クラス

このクラスは、リソース クリティカルな MFC 例外の基底クラスです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::CSimple例外](#csimpleexception)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#geterrormessage)|発生したエラーに関するテキストを提供します。|

## <a name="remarks"></a>解説

`CSimpleException`は、リソース クリティカルな MFC 例外の基本クラスであり、エラー メッセージの所有権と初期化を処理します。 次のクラスは`CSimpleException`、基本クラスとして使用されます。

|||
|-|-|
|[クラス](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|
|[クラスをサポートしていません。](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|
|[クラス](../../mfc/reference/cresourceexception-class.md)|Windows リソースが見つからないか、または作成可能でない|
|[CUserException クラス](../../mfc/reference/cuserexception-class.md)|リソースが見つからなかったことを示す例外|
|[クラスを無効にします。](../../mfc/reference/cinvalidargexception-class.md)|無効な引数を示す例外|

抽象`CSimpleException`基本クラスであるため、オブジェクトを`CSimpleException`直接宣言することはできません。 代わりに、前の表のような派生オブジェクトを宣言する必要があります。 独自の派生クラスを宣言する場合は、前のクラスをモデルとして使用します。

詳細については[、「CException クラス](../../mfc/reference/cexception-class.md)」および[「例外処理 (MFC)」](../../mfc/exception-handling-in-mfc.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a>::CSimple例外

コンストラクターです。

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*b自動削除*<br/>
オブジェクトのメモリがヒープに`CSimpleException`割り当てられている場合は、TRUE を指定します。 これにより、メンバー関数`CSimpleException`が呼び出されたときに、例外`Delete`を削除するオブジェクトが削除されます。 オブジェクトがスタック上`CSimpleException`にある場合、またはグローバルオブジェクトである場合は、FALSE を指定します。 この場合、`Delete`メンバー関数`CSimpleException`が呼び出されたときにオブジェクトは削除されません。

### <a name="remarks"></a>解説

通常、このコンストラクターを直接呼び出す必要はありません。 例外をスローする関数は`CException`、派生クラスのインスタンスを作成してそのコンストラクターを呼び出すか、または MFC の throw 関数[(AfxThrowFileException](exception-processing.md#afxthrowfileexception)など) のいずれかを使用して定義済みの型をスローする必要があります。

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a>をクリックします。

発生したエラーに関するテキストを提供します。

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
エラー メッセージを受け取るバッファーへのポインター。

*エラー*<br/>
バッファーが保持できる最大文字数 (NULL 終端文字を含む)。

*コンテキスト*<br/>
ヘルプ コンテキスト ID を受け取る UINT のアドレス。 NULL の場合、ID は返されません。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外の値を返します。それ以外の場合は 0 (エラー メッセージ テキストが使用できない場合)

### <a name="remarks"></a>解説

詳細については[、「CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)」を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[例外処理](../../mfc/exception-handling-in-mfc.md)
