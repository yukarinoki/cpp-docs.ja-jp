---
title: CDynamicStringAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessor
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
helpviewer_keywords:
- CDynamicStringAccessor class
- GetString method
- SetString method
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
ms.openlocfilehash: 891c80a7c21fd046fba393b494ed6d84f731db6f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498668"
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor クラス

データベーススキーマ (データベースの基になる構造) に関する知識がない場合に、データソースにアクセスできるようにします。

## <a name="syntax"></a>構文

```cpp
template< typename BaseType, DBTYPEENUM OleDbType >
class CDynamicStringAccessorT : public CDynamicAccessor
```

## <a name="requirements"></a>必要条件

**ヘッダー**: atldbcli. h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[GetString](#getstring)|指定された列データを文字列として取得します。|
|[SetString](#setstring)|指定された列データを文字列として設定します。|

## <a name="remarks"></a>注釈

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)は、プロバイダーによって報告されたネイティブ形式のデータを要求しますが、は、 `CDynamicStringAccessor` データストアからアクセスされるすべてのデータを文字列データとして取得するようにプロバイダーに要求します。 これは、データストアの内容の表示や印刷など、データストアの値の計算を必要としない単純なタスクに特に便利です。

データストア内の列データのネイティブな型は関係ありません。プロバイダーがデータ変換をサポートできる限り、データは文字列形式で提供されます。 プロバイダーがネイティブデータ型から文字列への変換をサポートしていない場合 (これは一般的ではありません)、要求を呼び出すと DB_S_ERRORSOCCURED 成功値が返され、対応する列の状態は DBSTATUS_E_CANTCONVERTVALUE の変換の問題を示します。

`CDynamicStringAccessor`列情報を取得するには、メソッドを使用します。 この列情報は、実行時にアクセサーを動的に作成するために使用します。

列情報は、このクラスによって作成および管理されるバッファーに格納されます。 [GetString](#getstring)を使用してバッファーからデータを取得するか、 [setstring](#setstring)を使用してバッファーに格納します。

動的アクセサークラスの使用例については、「 [動的アクセサーの使用](../../data/oledb/using-dynamic-accessors.md)」を参照してください。

## <a name="cdynamicstringaccessorgetstring"></a><a name="getstring"></a> CDynamicStringAccessor:: GetString

指定された列データを文字列として取得します。

### <a name="syntax"></a>構文

```cpp
BaseType* GetString(DBORDINAL nColumn) const throw();

BaseType* GetString(const CHAR* pColumnName) const throw();

BaseType* GetString(const WCHAR* pColumnName) const throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 値が0の場合は、ブックマーク列 (存在する場合) を参照します。

*pColumnName*<br/>
から列名を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

指定した列から取得した文字列値へのポインター。 値の型は `BaseType` で、_UNICODE が定義されているかどうかによって、 **CHAR** または **WCHAR** になります。 指定された列が見つからない場合は NULL を返します。

### <a name="remarks"></a>注釈

2番目のオーバーライド形式では、列名が ANSI 文字列として取得されます。 3番目のオーバーライド形式では、列名が Unicode 文字列として取得されます。

## <a name="cdynamicstringaccessorsetstring"></a><a name="setstring"></a> CDynamicStringAccessor:: SetString

指定された列データを文字列として設定します。

### <a name="syntax"></a>構文

```cpp
HRESULT SetString(DBORDINAL nColumn,
   BaseType* data) throw();

HRESULT SetString(const CHAR* pColumnName,
   BaseType* data) throw();

HRESULT SetString(const WCHAR* pColumnName,
   BaseType* data) throw();
```

#### <a name="parameters"></a>パラメーター

*n 列*<br/>
から列番号。 列番号は1から始まります。 特別な値0は、ブックマーク列 (存在する場合) を参照します。

*pColumnName*<br/>
から列名を含む文字列へのポインター。

*data*<br/>
から指定された列に書き込まれる文字列データへのポインター。

### <a name="return-value"></a>戻り値

指定された列を設定する文字列値へのポインター。 値の型は `BaseType` で、_UNICODE が定義されているかどうかによって、 **CHAR** または **WCHAR** になります。

### <a name="remarks"></a>注釈

2番目のオーバーライド形式では、列名が ANSI 文字列として取得され、3番目のオーバーライド形式では列名が Unicode 文字列として取得されます。

_SECURE_ATL が0以外の値を持つように定義されている場合、入力 *データ* 文字列が参照されるデータ列の許容最大長を超えると、ランタイムアサーションエラーが生成されます。 それ以外の場合、入力文字列は許容される最大長を超えた場合に切り捨てられます。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor クラス](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessorA クラス](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW クラス](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CXMLAccessor クラス](../../data/oledb/cxmlaccessor-class.md)
