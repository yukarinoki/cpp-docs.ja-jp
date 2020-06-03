---
title: CDataConnection クラス
ms.date: 03/27/2019
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
helpviewer_keywords:
- CDataConnection class
- CDataConnection class, constructor
- Copy method
- Open method
- OpenNewSession method
- BOOL operator
- operator bool
- BOOL operator
- operator bool
- CDataSource& operator
- operator & (CDataSource)
- CDataSource* operator
- operator * (CDataSource)
- operator CSession&
- CSession& operator
- operator CSession*
- CSession* operator
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
ms.openlocfilehash: fe954e218a099fa7956748904a4baa89f741c52f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368617"
---
# <a name="cdataconnection-class"></a>CDataConnection クラス

データ ソースとの接続を管理します。

## <a name="syntax"></a>構文

```cpp
class CDataConnection
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[接続](#cdataconnection)|コンストラクターです。 `CDataConnection`オブジェクトをインスタンス化して初期化します。|
|[コピー](#copy)|既存のデータ接続のコピーを作成します。|
|[開く](#open)|初期化文字列を使用してデータ ソースへの接続を開きます。|
|[新しいセッションを開く](#opennewsession)|現在の接続で新しいセッションを開きます。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 BOOL](#op_bool)|現在のセッションが開いているかどうかを判断します。|
|[オペレーター・ブール](#op_bool_ole)|現在のセッションが開いているかどうかを判断します。|
|[演算子 C データ ソース&](#op_cdata_amp)|含まれている`CDataSource`オブジェクトへの参照を返します。|
|[演算子 C データソース*](#op_cdata_star)|格納`CDataSource`されているオブジェクトへのポインターを返します。|
|[演算子 C セッション&](#op_csession_amp)|含まれている`CSession`オブジェクトへの参照を返します。|
|[演算子 CSession*](#op_csession_star)|格納`CSession`されているオブジェクトへのポインターを返します。|

## <a name="remarks"></a>解説

`CDataConnection`必要なオブジェクト (データ ソースとセッション) と、データ ソースへの接続時に必要な作業の一部をカプセル化するため、クライアントを作成する際に便利なクラスです。

を`CDataConnection`使用しない場合は、`CDataSource`オブジェクトを作成し、[その OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)メソッドを呼び出し[、CSession](../../data/oledb/csession-class.md)オブジェクトのインスタンスを作成し、[その Open](../../data/oledb/csession-open.md)メソッドを呼び出してから[、CCommand](../../data/oledb/ccommand-class.md)オブジェクトを作成し、その * メソッドを呼び出す必要があります`Open`。

では`CDataConnection`、接続オブジェクトを作成し、初期化文字列を渡してから、その接続を使用してコマンドを開くだけで済みます。 データベースへの接続を繰り返し使用する場合は、接続を開`CDataConnection`いたままにしておくことをお勧めします。

> [!NOTE]
> 複数のセッションを処理する必要があるデータベース アプリケーションを作成する場合は[、OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)を使用する必要があります。

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a>接続::Cデータ接続

`CDataConnection`オブジェクトをインスタンス化して初期化します。

### <a name="syntax"></a>構文

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>パラメーター

*Ds*<br/>
[in]既存のデータ接続への参照。

### <a name="remarks"></a>解説

最初のオーバーライドは、既定`CDataConnection`の設定で新しいオブジェクトを作成します。

2 番目のオーバーライドは`CDataConnection`、指定したデータ接続オブジェクトと同じ設定の新しいオブジェクトを作成します。

## <a name="cdataconnectioncopy"></a><a name="copy"></a>接続::コピー

既存のデータ接続のコピーを作成します。

### <a name="syntax"></a>構文

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>パラメーター

*Ds*<br/>
[in]コピーする既存のデータ接続への参照。

## <a name="cdataconnectionopen"></a><a name="open"></a>を開く

初期化文字列を使用してデータ ソースへの接続を開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>パラメーター

*文字列*<br/>
[in]データ ソースの初期化文字列。

### <a name="return-value"></a>戻り値

標準の HRESULT。

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a>接続::オープンニューセッション

現在の接続オブジェクトのデータ ソースを使用して新しいセッションを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
[イン/アウト]新しいセッション オブジェクトへの参照。

### <a name="remarks"></a>解説

新しいセッションでは、現在の接続オブジェクトに含まれているデータ ソース オブジェクトを親として使用し、データ ソースと同じ情報すべてにアクセスできます。

### <a name="return-value"></a>戻り値

標準の HRESULT。

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a>接続元::演算子ブール

現在のセッションが開いているかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>解説

**ブール値**を返します。 **TRUE は**、現在のセッションが開かされていることを意味します。**FALSE は**、現在のセッションが閉じられた状態であることを示します。

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a>コントロールブール (OLE DB)

現在のセッションが開いているかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
operator bool() throw();
```

### <a name="remarks"></a>解説

**ブール**値 (C++ データ型) の値を返します。 **true は**、現在のセッションが開いている場合を意味します。**false は**、現在のセッションが閉じられた状態であることを示します。

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a>次の操作を行います。&amp;

含まれている`CDataSource`オブジェクトへの参照を返します。

### <a name="syntax"></a>構文

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>解説

この演算子は、含まれている`CDataSource`オブジェクトへの参照を返し、参照が`CDataConnection`必要な場所`CDataSource`にオブジェクトを渡すことができます。

### <a name="example"></a>例

参照を受け取る関数`func`(以下など) がある場合は、`CDataSource&`を使用して`CDataConnection`オブジェクトを渡すことができます。 `CDataSource`

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a>Cデータ接続::演算子 Cデータソース*

格納`CDataSource`されているオブジェクトへのポインターを返します。

### <a name="syntax"></a>構文

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>解説

この演算子は、格納されている`CDataSource`オブジェクトへのポインターを返し、ポインターが`CDataConnection`必要な場所`CDataSource`にオブジェクトを渡すことができます。

使用例については[、演算子 CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)を参照してください。

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a>Cデータ接続::オペレーター Cセッション&amp;

含まれている`CSession`オブジェクトへの参照を返します。

### <a name="syntax"></a>構文

```cpp
operator const CSession&();
```

### <a name="remarks"></a>解説

この演算子は、含まれている`CSession`オブジェクトへの参照を返し、参照が`CDataConnection`必要な場所`CSession`にオブジェクトを渡すことができます。

### <a name="example"></a>例

参照を受け取る関数`func`(以下など) がある場合は、`CSession&`を使用して`CDataConnection`オブジェクトを渡すことができます。 `CSession`

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a>接続::演算子 C セッション*

格納`CSession`されているオブジェクトへのポインターを返します。

### <a name="syntax"></a>構文

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>解説

この演算子は、格納されている`CSession`オブジェクトへのポインターを返し、ポインターが`CDataConnection`必要な場所`CSession`にオブジェクトを渡すことができます。

### <a name="example"></a>例

使用例については[、演算子 CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
