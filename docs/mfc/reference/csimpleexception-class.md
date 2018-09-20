---
title: CSimpleException クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f25928243c8086462f4f35b47dee5239a3a240bf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446999"
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

## <a name="remarks"></a>Remarks

`CSimpleException` リソース クリティカルな MFC 例外の基本クラスですし、所有権とエラー メッセージの初期化を処理します。 次のクラスの使用`CSimpleException`その基本クラスとして。

|||
|-|-|
|[CMemoryException クラス](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|
|[CNotSupportedException クラス](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|
|[CResourceException クラス](../../mfc/reference/cresourceexception-class.md)|見つからないか、またはできない Windows リソース|
|[CUserException クラス](../../mfc/reference/cuserexception-class.md)|リソースを示す例外が見つかりませんでした。|
|[CInvalidArgException クラス](../../mfc/reference/cinvalidargexception-class.md)|無効な引数を示す例外|

`CSimpleException`抽象基本クラスでは、宣言することはできません、`CSimpleException`オブジェクトに直接します。 代わりに、前の表にあるなどの派生オブジェクトを宣言する必要があります。 派生クラスを宣言している場合は、モデルとして前のクラスを使用します。

詳細については、次を参照してください。、 [CException クラス](../../mfc/reference/cexception-class.md)トピックと[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>要件

**ヘッダー:** afx.h

##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException

コンストラクターです。

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>パラメーター

*bAutoDelete*<br/>
場合は TRUE を指定のメモリ、`CSimpleException`オブジェクトがヒープに割り当てられています。 これにより、`CSimpleException`ときに削除するオブジェクト、`Delete`例外を削除するメンバー関数が呼び出されます。 場合は FALSE を指定、`CSimpleException`オブジェクトがスタック上にまたはグローバル オブジェクトです。 ここで、`CSimpleException`オブジェクトができない場合に削除されます、`Delete`メンバー関数が呼び出されます。

### <a name="remarks"></a>Remarks

このコンス トラクターを直接呼び出す必要は通常ありません。 例外をスローする関数のインスタンスを作成する必要があります、 `CException`-クラスを派生し、コンス トラクターまたはそれを呼び出す必要があります、MFC のいずれかを使用してスロー関数など[AfxThrowFileException](exception-processing.md#afxthrowfileexception)、定義済みの型をスローします。

##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage

発生したエラーに関するテキストを提供するには、このメンバー関数を呼び出します。

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszError*<br/>
エラー メッセージを受け取るバッファーへのポインター。

*nMaxError*<br/>
NULL ターミネータを含めた、バッファーが保持できる文字の最大数。

*pnHelpContext*<br/>
ヘルプ コンテキスト ID を受け取る UINT のアドレス NULL の場合、ID は返されません。

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合 0 の場合、エラー メッセージ テキストは使用できます。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CException クラス](../../mfc/reference/cexception-class.md)<br/>
[例外処理](../../mfc/exception-handling-in-mfc.md)



