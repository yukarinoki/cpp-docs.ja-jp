---
title: CDaoException クラス
ms.date: 11/04/2016
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
ms.openlocfilehash: 224ce79094b174d0bd011bd89afbcfe6fb7735d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585916"
---
# <a name="cdaoexception-class"></a>CDaoException クラス

データ アクセス オブジェクト (DAO: Data Accsess Object) を基にした MFC データベース クラスから発生する例外条件を表します。

## <a name="syntax"></a>構文

```
class CDaoException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDaoException::CDaoException](#cdaoexception)|`CDaoException` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[あります。](#geterrorcount)|データベース エンジンのエラーのコレクション内には、エラーの数を返します。|
|[CDaoException::GetErrorInfo](#geterrorinfo)|エラーのコレクション内には、特定のエラー オブジェクトに関するエラー情報を返します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO クラスで何らかのエラーの拡張エラー コードが含まれています。|
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|ポインターを[CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) DAO エラーの 1 つのオブジェクトに関する情報を含むオブジェクト。|
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode)エラーに関連付けられた値。|

## <a name="remarks"></a>Remarks

クラスには、例外の原因を調べて使用できるパブリック データ メンバーが含まれています。 `CDaoException` オブジェクトが構築され、DAO データベース クラスのメンバー関数によってスローされます。

> [!NOTE]
>  DAO データベース クラスは、ベースの開いているデータベースの接続 (ODBC) で MFC データベース クラスとは異なります。 DAO データベース クラスの名前には、"CDao"プレフィックスが付いています。 DAO クラスで ODBC データ ソースのアクセスできます。 一般に、DAO に基づいて MFC クラスは ODBC; に基づいて MFC クラスよりもより高機能ですDAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを含む、データにアクセスできます。 DAO ベースのクラスには、DAO を直接呼び出すことがなく、クラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。 ODBC クラスによってスローされた例外については、次を参照してください。 [CDBException](../../mfc/reference/cdbexception-class.md)します。

スコープ内で例外オブジェクトにアクセスすることができます、[キャッチ](../../mfc/reference/exception-processing.md#catch)式。 スローすることもできます`CDaoException`で独自のコードからのオブジェクト、 [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)グローバル関数。

Mfc では、DAO のすべてのエラーが型の例外として表される`CDaoException`します。 この型の例外をキャッチした場合に使用できます`CDaoException`DAO データベース エンジンのエラー コレクションに格納されているエラー オブジェクトから情報を取得するメンバー関数。 各エラーが発生すると、1 つ以上のエラー オブジェクトがエラー コレクションに配置されます。 (通常 1 つだけのエラー オブジェクトがコレクション内には、複数のエラー オブジェクトを取得する可能性が高くなりますが、ODBC データ ソースを使用している場合)。DAO の別の操作では、エラーを生成するとき、エラーのコレクションをクリアし、新しいエラー オブジェクトがエラー コレクションに配置します。 エラーが発生しない DAO 操作は、エラー コレクションに影響を与えるありません。

DAO のエラー コード、DAOERR ファイルを参照してください。H. 関連情報については、「トラップ可能なデータ アクセス エラー」DAO ヘルプのトピックを参照してください。

[全般]、またはについての例外処理の詳細については`CDaoException`オブジェクトは、記事をご覧ください[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)と[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。 2 番目の記事には、DAO での例外処理を示したサンプル コードが含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

##  <a name="cdaoexception"></a>  CDaoException::CDaoException

`CDaoException` オブジェクトを構築します。

```
CDaoException();
```

### <a name="remarks"></a>Remarks

通常、フレームワークは、そのコードが例外をスローする場合、例外オブジェクトを作成します。 ほとんどの例外オブジェクトを明示的に作成する必要があります。 スローする場合、`CDaoException`グローバル関数を呼び出す独自のコードから[AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)します。

ただし、MFC クラスをカプセル化する DAO インターフェイス ポインターを使用して DAO の直接呼び出しを行う場合、例外オブジェクトを明示的に作成する場合があります。 その場合は、DAO からエラー情報を取得する必要があります。 ワークスペースのデータベース コレクションに DAODatabases インターフェイスを使用して、DAO メソッドを呼び出すと、DAO でエラーが発生したとします。

##### <a name="to-retrieve-the-dao-error-information"></a>DAO のエラー情報を取得するには

1. `CDaoException` オブジェクトを構築します。

1. 例外オブジェクトの[GetErrorCount](#geterrorcount)は、データベース エンジンのエラーのコレクション内のエラー オブジェクトの数を調べます。 (通常 1 つだけ、ODBC データ ソースを使用している場合を除き、します)。

1. 例外オブジェクトの[GetErrorInfo](#geterrorinfo)例外オブジェクトを使用して、コレクション内のインデックスを使用して、一度に 1 つの特定のエラー オブジェクトを取得するメンバー関数。 例外オブジェクトを 1 つの DAO エラー オブジェクトをプロキシとして考えます。

1. 現在の確認[CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体`GetErrorInfo`で返します、 [m_pErrorInfo](#m_perrorinfo)データ メンバー。 そのメンバーは、DAO エラーに関する情報を提供します。

1. データ ソースの場合は、手順 3. および 4. エラー オブジェクトの詳細については、必要に応じてを繰り返します。

1. ヒープ上の例外オブジェクトを構築する場合にそれを削除、**削除**が完了したら、演算子。

MFC DAO クラスでのエラー処理の詳細については、この記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。

##  <a name="geterrorcount"></a>  あります。

DAO データベース エンジンのエラーのコレクションのオブジェクトのエラーの数を取得するには、このメンバー関数を呼び出します。

```
short GetErrorCount();
```

### <a name="return-value"></a>戻り値

DAO データベース エンジンのエラーのコレクションのオブジェクトのエラーの数。

### <a name="remarks"></a>Remarks

この情報は、各コレクションの 1 つまたは複数 DAO エラー オブジェクトを取得するエラーのコレクションをループ処理する場合に便利です。 インデックスまたは DAO のエラー番号でエラー オブジェクトを取得する、 [GetErrorInfo](#geterrorinfo)メンバー関数。

> [!NOTE]
>  通常のエラー コレクションには 1 つだけのエラー オブジェクトが存在します。 ODBC データ ソースを使用する場合があります 1 つ以上。

##  <a name="geterrorinfo"></a>  CDaoException::GetErrorInfo

エラーのコレクション内には、特定のエラー オブジェクトに関するエラー情報を返します。

```
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
インデックスで検索する場合、データベース エンジンのエラー コレクションにエラー情報のインデックス。

### <a name="remarks"></a>Remarks

次の種類の例外に関する情報を取得するには、このメンバー関数を呼び出します。

- エラー コード

- ソース

- 説明

- ヘルプ ファイル

- ヘルプ コンテキスト

`GetErrorInfo` 例外オブジェクトの情報を格納`m_pErrorInfo`データ メンバー。 返される情報の簡単な説明を参照してください。 [m_pErrorInfo](#m_perrorinfo)します。 型の例外をキャッチする場合`CDaoException`、MFC によってスローされた、`m_pErrorInfo`メンバーが既に入力されます。 DAO の直接呼び出しを選択した場合は、例外オブジェクトを呼び出す必要があります`GetErrorInfo`メンバー関数を`m_pErrorInfo`します。 詳細については、次を参照してください。、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体。

DAO 例外、およびコード例については、この記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。

##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError

MFC 拡張エラー コードが含まれています。

### <a name="remarks"></a>Remarks

MFC DAO クラスの特定のコンポーネントがであったがの場合、このコードが提供されます。

指定できる値は次のとおりです。

- 最新の操作は、MFC になりませんでした NO_AFX_DAO_ERROR は拡張エラーです。 ただし、操作でしたが生成 DAO または OLE から他のエラーを確認する必要がありますので[m_pErrorInfo](#m_perrorinfo)や[m_scode](#m_scode)します。

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC は、Microsoft Jet データベース エンジンを初期化できませんでした。 OLE は初期化に失敗した可能性があります。 またはそれが解除された可能性が DAO データベース エンジンのオブジェクトのインスタンスを作成することです。 これらの問題には、DAO または OLE のいずれかの不適切なインストールは、通常お勧めします。

- AFX_DAO_ERROR_DFX_BIND DAO レコード フィールド エクス (チェンジ DFX) 関数の呼び出しで使用されているアドレスが存在しないか無効です (アドレスがデータ バインドには使用されません)。 DFX 呼び出しで無効なアドレスに合格する可能性があります。 またはアドレスが無効になる可能性 DFX 操作します。

- クエリ定義または、開いている状態ではないテーブル定義オブジェクトに基づくレコード セットを AFX_DAO_ERROR_OBJECT_NOT_OPEN を開こうとしました。

##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo

ポインターが含まれています、`CDaoErrorInfo`前回を呼び出すことによって取得した DAO エラー オブジェクト情報を提供する構造体[GetErrorInfo](#geterrorinfo)します。

### <a name="remarks"></a>Remarks

このオブジェクトには、次の情報が含まれています。

|CDaoErrorInfo メンバー|情報|説明|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|エラー コード|DAO のエラー コード|
|`m_strSource`|ソース|オブジェクトまたはアプリケーション エラーの発生源の名前|
|`m_strDescription`|説明|エラーに関連付けられているわかりやすい文字列|
|`m_strHelpFile`|ヘルプ ファイル|ユーザーが、問題に関する情報を取得できる、Windows ヘルプ ファイルへのパス|
|`m_lHelpContext`|ヘルプ コンテキスト|DAO のヘルプ ファイルのトピックのコンテキスト ID|

含まれる情報の詳細について、`CDaoErrorInfo`オブジェクトを参照してください、 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体。

##  <a name="m_scode"></a>  CDaoException::m_scode

型の値を含む`SCODE`エラーを説明します。

### <a name="remarks"></a>Remarks

これは、OLE コードです。 ほとんどの場合、MFC または DAO エラーの詳細については、他の使用可能なため、この値を使用する必要があります頻度の低い`CDaoException`データ メンバー。

SCODE については、トピックを参照してください。 [OLE エラー コードの構造](/windows/desktop/com/structure-of-com-error-codes)Windows SDK に含まれています。 SCODE のデータ型は、HRESULT のデータ型にマップします。

## <a name="see-also"></a>関連項目

[CException クラス](../../mfc/reference/cexception-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CException クラス](../../mfc/reference/cexception-class.md)
