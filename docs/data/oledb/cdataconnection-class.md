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
ms.openlocfilehash: 385445081f84f65ff7030466a238a5a96abd63be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212065"
---
# <a name="cdataconnection-class"></a>CDataConnection クラス

データソースとの接続を管理します。

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
|[CDataConnection](#cdataconnection)|コンストラクターです。 `CDataConnection` オブジェクトをインスタンス化し、初期化します。|
|[Copy](#copy) に設定する必要があります|既存のデータ接続のコピーを作成します。|
|[[ファイル]](#open)|初期化文字列を使用して、データソースへの接続を開きます。|
|[OpenNewSession](#opennewsession)|現在の接続で新しいセッションを開きます。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[BOOL 演算子](#op_bool)|現在のセッションが開いているかどうかを判断します。|
|[operator bool](#op_bool_ole)|現在のセッションが開いているかどうかを判断します。|
|[operator CDataSource &](#op_cdata_amp)|格納されている `CDataSource` オブジェクトへの参照を返します。|
|[operator CDataSource *](#op_cdata_star)|格納されている `CDataSource` オブジェクトへのポインターを返します。|
|[operator CSession &](#op_csession_amp)|格納されている `CSession` オブジェクトへの参照を返します。|
|[operator CSession *](#op_csession_star)|格納されている `CSession` オブジェクトへのポインターを返します。|

## <a name="remarks"></a>解説

`CDataConnection` は、必要なオブジェクト (データソースとセッション) とデータソースへの接続時に実行する必要がある作業の一部をカプセル化するため、クライアントを作成するのに便利なクラスです。

`CDataConnection`ない場合は、`CDataSource` オブジェクトを作成し、その[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)メソッドを呼び出してから、 [CSession](../../data/oledb/csession-class.md)オブジェクトのインスタンスを作成し、その[Open](../../data/oledb/csession-open.md)メソッドを呼び出して、 [CCommand](../../data/oledb/ccommand-class.md)オブジェクトを作成し、その `Open`* メソッドを呼び出す必要があります。

`CDataConnection`では、接続オブジェクトを作成し、それに初期化文字列を渡してから、その接続を使用してコマンドを開くだけです。 データベースへの接続を繰り返し使用する場合は、接続を開いたままにしておくことをお勧めします。これにより、`CDataConnection` の便利な方法が提供されます。

> [!NOTE]
>  複数のセッションを処理する必要があるデータベースアプリケーションを作成する場合は、 [Opennewsession](../../data/oledb/cdataconnection-opennewsession.md)を使用する必要があります。

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a>CDataConnection:: CDataConnection

`CDataConnection` オブジェクトをインスタンス化し、初期化します。

### <a name="syntax"></a>構文

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>パラメーター

*ds*<br/>
から既存のデータ接続への参照。

### <a name="remarks"></a>解説

最初のオーバーライドでは、既定の設定を使用して新しい `CDataConnection` オブジェクトを作成します。

2番目のオーバーライドは、指定したデータ接続オブジェクトと同等の設定を持つ新しい `CDataConnection` オブジェクトを作成します。

## <a name="cdataconnectioncopy"></a><a name="copy"></a>CDataConnection:: Copy

既存のデータ接続のコピーを作成します。

### <a name="syntax"></a>構文

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>パラメーター

*ds*<br/>
からコピーする既存のデータ接続への参照。

## <a name="cdataconnectionopen"></a><a name="open"></a>CDataConnection:: Open

初期化文字列を使用して、データソースへの接続を開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>パラメーター

*szInitString*<br/>
からデータソースの初期化文字列。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a>CDataConnection:: OpenNewSession

現在の接続オブジェクトのデータソースを使用して、新しいセッションを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
[入力/出力]新しいセッションオブジェクトへの参照。

### <a name="remarks"></a>解説

新しいセッションでは、現在の接続オブジェクトに含まれているデータソースオブジェクトを親として使用し、データソースと同じすべての情報にアクセスできます。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a>CDataConnection:: operator BOOL

現在のセッションが開いているかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>解説

**BOOL** (MFC typedef) 値を返します。 **TRUE**は、現在のセッションが開いていることを示します。**FALSE**は、現在のセッションが閉じられていることを示します。

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a>CDataConnection:: operator bool (OLE DB)

現在のセッションが開いているかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
operator bool() throw();
```

### <a name="remarks"></a>解説

**ブール**値 (C++データ型) を返します。 **true**は、現在のセッションが開いていることを示します。**false**は、現在のセッションが閉じられていることを示します。

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a>CDataConnection:: operator CDataSource&amp;

格納されている `CDataSource` オブジェクトへの参照を返します。

### <a name="syntax"></a>構文

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>解説

この演算子は、含まれている `CDataSource` オブジェクトへの参照を返します。これにより、`CDataSource` 参照が想定される `CDataConnection` オブジェクトを渡すことができます。

### <a name="example"></a>例

`CDataSource` 参照を受け取る関数 (`func` など) がある場合は、代わりに `CDataSource&` を使用して `CDataConnection` オブジェクトを渡すことができます。

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a>CDataConnection:: operator CDataSource *

格納されている `CDataSource` オブジェクトへのポインターを返します。

### <a name="syntax"></a>構文

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>解説

この演算子は、含まれている `CDataSource` オブジェクトへのポインターを返します。これにより、`CDataSource` ポインターが必要な `CDataConnection` オブジェクトを渡すことができます。

使用例については、「 [Operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) 」を参照してください。

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a>CDataConnection:: operator CSession&amp;

格納されている `CSession` オブジェクトへの参照を返します。

### <a name="syntax"></a>構文

```cpp
operator const CSession&();
```

### <a name="remarks"></a>解説

この演算子は、含まれている `CSession` オブジェクトへの参照を返します。これにより、`CSession` 参照が想定される `CDataConnection` オブジェクトを渡すことができます。

### <a name="example"></a>例

`CSession` 参照を受け取る関数 (`func` など) がある場合は、代わりに `CSession&` を使用して `CDataConnection` オブジェクトを渡すことができます。

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a>CDataConnection:: operator CSession *

格納されている `CSession` オブジェクトへのポインターを返します。

### <a name="syntax"></a>構文

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>解説

この演算子は、含まれている `CSession` オブジェクトへのポインターを返します。これにより、`CSession` ポインターが必要な `CDataConnection` オブジェクトを渡すことができます。

### <a name="example"></a>例

使用例については、「 [Operator CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) 」を参照してください。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
