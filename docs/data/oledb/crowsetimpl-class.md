---
title: CRowsetImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- CRowsetImpl class
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eece641adacd6ce918929366c4fc6dc78105e71a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098720"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl クラス
多くの実装インターフェイスの多重継承を必要とせず、標準の OLE DB 行セットの実装を提供します。  
  
## <a name="syntax"></a>構文

```cpp
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl <T, IRowset>   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ユーザーのクラスから派生した`CRowsetImpl`です。  
  
 `Storage`  
 ユーザー レコード クラスです。  
  
 `CreatorClass`  
 行セットのプロパティを含むクラス通常はコマンド。  
  
 `ArrayType`  
 行セットのデータの記憶域として機能するクラスです。 このパラメーターの既定値`CAtlArray`が必要な機能をサポートする任意のクラスを指定できます。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|文字列を抽出、 **DBID**をコピーし、`bstr`で渡されます。|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|検証し、格納、 **DBID**2 つの文字列で $s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md))。|  
  
### <a name="overridable-methods"></a>オーバーライド可能なメソッド  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|特定のクライアント要求の列情報を取得します。|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|いずれかまたは両方のパラメーターには、文字列値が含まれている場合を確認するためのチェックは、データ メンバーに文字列値をコピー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|いずれかを参照またはその両方をチェック**DBID**s が、文字列値を含めるし、場合は、そのデータ メンバーにコピー [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)と[その](../../data/oledb/crowsetimpl-m-strindextext.md)です。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|既定では、`CAtlArray`へのユーザー レコードのテンプレート引数で templatizes を`CRowsetImpl`です。 変更することによって、配列型の別のクラスを使用できます、`ArrayType`へのテンプレート引数`CRowsetImpl`です。|  
|[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|行セットの最初のコマンドが含まれています。|  
|[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|行セットの最初のインデックスが含まれています。|  
  
## <a name="remarks"></a>コメント  
 `CRowsetImpl` 静的キャストの形式での上書きを提供します。 メソッドは、指定された行セットがコマンド テキストを検証する方法を制御します。 独自に作成することができます`CRowsetImpl`-複数継承の実装インターフェイスをすることでクラスのスタイルを設定します。 唯一の方法を実装を提供する必要があります**Execute**です。 行セットの種類を作成することによって作成者メソッドに異なる署名が要求するは**Execute**です。 たとえば、使用している場合、 `CRowsetImpl`-スキーマ行セットを実装するクラスを派生、 **Execute**メソッドは、次の署名には。  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 作成する場合、 `CRowsetImpl`-コマンドまたはセッションの行セットを実装するクラスを派生、 **Execute**メソッドは、次の署名になります。  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 いずれかを実装する、 `CRowsetImpl`-派生**Execute**メソッド、内部データ バッファーを設定する必要があります ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md))。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h