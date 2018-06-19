---
title: CCommand クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
dev_langs:
- C++
helpviewer_keywords:
- CCommand class
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 667e86c173a7001ae22036cb1f0dd8f3fbfcf6a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096900"
---
# <a name="ccommand-class"></a>CCommand クラス
設定し、コマンドを実行するメソッドを提供します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CNoAccessor,  
          template <typename T> class TRowset = CRowset,  
          class TMultiple = CNoMultipleResults>  
class CCommand :   
           public CAccessorRowset <TAccessor, TRowset>,  
           public CCommandBase,  
           public TMultiple  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 アクセサー クラスの型 (など`CDynamicParameterAccessor`、 `CDynamicStringAccessor`、または`CEnumeratorAccessor`) を使用するコマンドを追加することです。 既定値は`CNoAccessor`がクラスいないパラメーターをサポートするか指定します列を出力します。  
  
 `TRowset`  
 行セット クラスの型 (など`CArrayRowset`または`CNoRowset`) を使用するコマンドを追加することです。 既定値は、`CRowset` です。  
  
 `TMultiple`  
 複数の結果を返すことができる OLE DB コマンドを使用して、指定[CMultipleResults](../../data/oledb/cmultipleresults-class.md)です。 それ以外の場合、使用[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)です。 詳細については、「 [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[閉じる](../../data/oledb/ccommand-close.md)|現在のコマンドを閉じます。|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|セットを複数の結果を使用するときに、次の結果をフェッチします。|  
|[開く](../../data/oledb/ccommand-open.md)|実行し、必要に応じて、コマンドをバインドします。|  
  
### <a name="inherited-methods"></a>継承されたメソッド  
  
|||  
|-|-|  
|[作成します。](../../data/oledb/ccommand-create.md)|指定したセッションの新しいコマンドを作成し、コマンド テキストを設定します。|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|新しいコマンドを作成します。|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|コマンドのパラメーター、その名前、およびそれらの種類の一覧を取得します。|  
|[準備します。](../../data/oledb/ccommand-prepare.md)|検証し、現在のコマンドを最適化できます。|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|必要に応じて、パラメーター アクセサーを解放し、次のコマンドを解放します。|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|各コマンド パラメーターのネイティブな型を指定します。|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|現在のコマンドの実行プランを破棄します。|  
  
## <a name="remarks"></a>コメント  
 パラメーターに基づく操作を実行またはコマンドを実行する必要がある場合は、このクラスを使用します。 だけを開くには単純な行セットする必要がある場合を使用して[CTable](../../data/oledb/ctable-class.md)代わりにします。  
  
 使用して、アクセサー クラスでは、パラメーターとデータを連結する方法を決定します。  
  
 注ことことはできませんストアド プロシージャを使用する OLE DB Provider for Jet そのプロバイダーがサポートしていないためには、(定数だけをクエリ文字列で使用) の手順が格納されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)