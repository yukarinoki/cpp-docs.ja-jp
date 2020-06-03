---
title: クラスを呼び出す
ms.date: 09/17/2019
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
ms.openlocfilehash: 935d7870d68554d702e2ad762e83343cb518b2b8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754731"
---
# <a name="cdaoexception-class"></a>クラスを呼び出す

データ アクセス オブジェクト (DAO: Data Accsess Object) を基にした MFC データベース クラスから発生する例外条件を表します。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

## <a name="syntax"></a>構文

```
class CDaoException : public CException
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::CDao例外](#cdaoexception)|`CDaoException` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#geterrorcount)|データベース エンジンの Errors コレクション内のエラーの数を返します。|
|[を指定します。](#geterrorinfo)|Errors コレクション内の特定のエラー オブジェクトに関するエラー情報を返します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[カダオ例外::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO クラスのエラーに対する拡張エラー コードが含まれています。|
|[カダオ例外::m_pErrorInfo](#m_perrorinfo)|1 つの DAO エラー オブジェクトに関する情報を格納する[CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)オブジェクトへのポインター。|
|[カダオ例外::m_scode](#m_scode)|エラーに関連付けられている[SCODE](#m_scode)値。|

## <a name="remarks"></a>解説

このクラスには、例外の原因を特定するために使用できるパブリック データ メンバーが含まれています。 `CDaoException`オブジェクトは、DAO データベース クラスのメンバー関数によって構築およびスローされます。

> [!NOTE]
> DAO データベース クラスは、オープン データベース接続 (ODBC) に基づく MFC データベース クラスとは異なります。 DAO データベースクラス名には、すべて "CDao" というプレフィックスが付いています。 DAO クラスを使用して ODBC データ ソースにアクセスすることはできます。 一般に、DAO に基づく MFC クラスは、ODBC に基づく MFC クラスよりも能力が高くなります。DAO ベースのクラスは、ODBC ドライバを使用して、独自のデータベース エンジンを介してデータにアクセスできます。 DAO ベースのクラスでは、DAO を直接呼び出すことなく、クラスを介してテーブルを追加するなど、データ定義言語 (DDL) 操作もサポートしています。 ODBC クラスによってスローされる例外については、「 [CDBException](../../mfc/reference/cdbexception-class.md)」を参照してください。

[CATCH](../../mfc/reference/exception-processing.md#catch)式のスコープ内で例外オブジェクトにアクセスできます。 `CDaoException` [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)グローバル関数を使用して、独自のコードからオブジェクトをスローすることもできます。

MFC では、DAO エラーはすべて、型`CDaoException`の例外として表されます。 この型の例外をキャッチすると、メンバー関数を使用`CDaoException`して、データベース エンジンの Errors コレクションに格納されている DAO エラー オブジェクトから情報を取得できます。 各エラーが発生すると、Errors コレクションに 1 つ以上のエラー オブジェクトが配置されます。 (通常、コレクションには 1 つのエラー オブジェクトのみが含まれます。別の DAO 操作でエラーが発生すると、Errors コレクションがクリアされ、新しいエラー オブジェクトが Errors コレクションに格納されます。 エラーを生成しない DAO 操作は、Errors コレクションには影響しません。

DAO エラー コードについては、DAOERR ファイルを参照してください。H。 関連情報については、DAO ヘルプの「トラップ可能なデータ アクセス エラー」を参照してください。

例外処理全般または`CDaoException`オブジェクトの詳細については、「[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md) 」および「[例外: データベース例外](../../mfc/exceptions-database-exceptions.md)」を参照してください。 2 番目の資料には、DAO での例外処理を示すコード例が含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a>::CDao例外

`CDaoException` オブジェクトを構築します。

```
CDaoException();
```

### <a name="remarks"></a>解説

通常、フレームワークは、コードが例外をスローするときに例外オブジェクトを作成します。 例外オブジェクトを明示的に作成する必要はめったにありません。 独自のコードから を`CDaoException`スローする場合は、グローバル関数[AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)を呼び出します。

ただし、MFC クラスがカプセル化する DAO インターフェイス ポインタを介して DAO を直接呼び出す場合は、例外オブジェクトを明示的に作成できます。 その場合は、DAO からエラー情報を取得する必要があります。 DAO で、DAODatabases インターフェイスを使用してワークスペースの Databases コレクションに対して DAO メソッドを呼び出すと、エラーが発生したとします。

##### <a name="to-retrieve-the-dao-error-information"></a>DAO エラー情報を取得するには

1. `CDaoException` オブジェクトを構築します。

1. 例外オブジェクトの[GetErrorCount](#geterrorcount)メンバー関数を呼び出して、データベース エンジンの Errors コレクション内のエラー オブジェクトの数を調べます。 (通常は、ODBC データ ソースを使用していない場合は 1 つだけです)。

1. 例外オブジェクトを使用して、例外オブジェクトの[GetErrorInfo](#geterrorinfo)メンバー関数を呼び出して、コレクション内のインデックスを使用して一度に 1 つの特定のエラー オブジェクトを取得します。 例外オブジェクトは、1 つの DAO エラー オブジェクトのプロキシと考えてください。

1. [m_pErrorInfo](#m_perrorinfo)データ メンバーで返される`GetErrorInfo`現在の[CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体を調べます。 そのメンバーは、DAO エラーに関する情報を提供します。

1. ODBC データ・ソースの場合、必要に応じてステップ 3 と 4 を繰り返して、より多くのエラー・オブジェクトを探します。

1. ヒープに例外オブジェクトを構築した場合は、終了時に delete 演算子を使用して**削除**します。

MFC DAO クラスのエラー処理の詳細については、「例外 :[データベース例外](../../mfc/exceptions-database-exceptions.md)」を参照してください。

## <a name="cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a>を使用します。

データベース エンジンの Errors コレクション内の DAO エラー オブジェクトの数を取得します。

```
short GetErrorCount();
```

### <a name="return-value"></a>戻り値

データベース エンジンの Errors コレクション内の DAO エラー オブジェクトの数。

### <a name="remarks"></a>解説

この情報は、Errors コレクションをループ処理して、コレクション内の 1 つ以上の DAO エラー オブジェクトを取得する場合に役立ちます。 エラー オブジェクトをインデックスまたは DAO エラー番号で取得するには[、GetErrorInfo](#geterrorinfo)メンバー関数を呼び出します。

> [!NOTE]
> 通常、Errors コレクションにはエラー オブジェクトが 1 つだけ存在します。 ただし、ODBC データ ソースを使用している場合は、複数のデータ ソースが存在する可能性があります。

## <a name="cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a>を指定します。

Errors コレクション内の特定のエラー オブジェクトに関するエラー情報を返します。

```cpp
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
データベース エンジンの Errors コレクション内のエラー情報のインデックスです。

### <a name="remarks"></a>解説

例外に関する次の種類の情報を取得するには、このメンバー関数を呼び出します。

- エラー コード

- source

- 説明

- ヘルプ ファイル

- ヘルプ コンテキスト

`GetErrorInfo`は、例外オブジェクトの`m_pErrorInfo`データ メンバーに情報を格納します。 返される情報の簡単な説明については[、「m_pErrorInfo」](#m_perrorinfo)を参照してください。 MFC によってスローされた型`CDaoException`の例外をキャッチする`m_pErrorInfo`場合、メンバーは既に入力されます。 DAO を直接呼び出す場合は、例外オブジェクトの`GetErrorInfo`メンバー関数を自分で呼び`m_pErrorInfo`出して を埋める必要があります。 詳細については、[構造体](../../mfc/reference/cdaoerrorinfo-structure.md)を参照してください。

DAO の例外とコード例については、「[例外: データベース](../../mfc/exceptions-database-exceptions.md)例外 」を参照してください。

## <a name="cdaoexceptionm_nafxdaoerror"></a><a name="m_nafxdaoerror"></a>カダオ例外::m_nAfxDaoError

MFC 拡張エラー コードが含まれています。

### <a name="remarks"></a>解説

このコードは、MFC DAO クラスの特定のコンポーネントが誤った場合に提供されます。

次のいずれかの値になります。

- NO_AFX_DAO_ERROR 最新の操作では、MFC 拡張エラーが発生しませんでした。 しかし、この操作によって DAO または OLE から他のエラーが発生する可能性があるため[、m_pErrorInfo](#m_perrorinfo)チェックして、場合によっては[m_scode](#m_scode)する必要があります。

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC は、Jet データベース エンジンを初期化できませんでした。 OLE が初期化に失敗したか、DAO データベース エンジン オブジェクトのインスタンスを作成できなかった可能性があります。 これらの問題は、通常、DAO または OLE のインストールが正しく行かずいことを示しています。

- AFX_DAO_ERROR_DFX_BIND DAO レコード フィールド エクスチェンジ (DFX) 関数呼び出しで使用されるアドレスが存在しないか、無効です (アドレスがデータのバインドに使用されていません)。 DFX コールで不正なアドレスを渡したか、DFX 操作の間にアドレスが無効になっている可能性があります。

- AFX_DAO_ERROR_OBJECT_NOT_OPEN クエリ定義または開いている状態ではないテーブル定義オブジェクトに基づいてレコードセットを開こうとしました。

## <a name="cdaoexceptionm_perrorinfo"></a><a name="m_perrorinfo"></a>カダオ例外::m_pErrorInfo

[GetErrorInfo](#geterrorinfo)を`CDaoErrorInfo`呼び出して最後に取得した DAO エラー オブジェクトに関する情報を提供する構造体へのポインターが含まれています。

### <a name="remarks"></a>解説

このオブジェクトには、次の情報が含まれています。

|メンバー|情報|意味|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|エラー コード|DAO エラー コード|
|`m_strSource`|source|エラーを生成したオブジェクトまたはアプリケーションの名前|
|`m_strDescription`|説明|エラーに関連付けられた説明文字列|
|`m_strHelpFile`|ヘルプ ファイル|ユーザーが問題に関する情報を取得できる Windows ヘルプ ファイルへのパス|
|`m_lHelpContext`|ヘルプ コンテキスト|DAO ヘルプ ファイル内のトピックのコンテキスト ID|

`CDaoErrorInfo`オブジェクトに含まれる情報の詳細については[、CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)構造体を参照してください。

## <a name="cdaoexceptionm_scode"></a><a name="m_scode"></a>カダオ例外::m_scode

エラーを説明する型`SCODE`の値を格納します。

### <a name="remarks"></a>解説

これは OLE コードです。 ほとんどの場合、より詳細な MFC または DAO エラー情報が他`CDaoException`のデータ メンバで使用できるため、この値を使用する必要はほとんどありません。

SCODE の詳細については、Windows SDK の[OLE エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。 SCODE データ型は、HRESULT データ型にマップされます。

## <a name="see-also"></a>関連項目

[クラスの例外](../../mfc/reference/cexception-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスの例外](../../mfc/reference/cexception-class.md)
