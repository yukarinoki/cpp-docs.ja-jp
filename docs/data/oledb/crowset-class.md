---
title: CRowset クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>
- CRowset
- ATL::CRowset
- ATL::CRowset<TAccessor>
- ATL.CRowset
dev_langs:
- C++
helpviewer_keywords:
- CRowset class
ms.assetid: b0228a90-b8dd-47cc-b397-8d4c15c1e7f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5c9a23c2e879f0d2fe1add1a970c64f6fbcc27b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="crowset-class"></a>CRowset クラス
OLE DB 行セット オブジェクトおよび関連するいくつかをカプセル化インターフェイスし、行セットのデータの操作メソッドを提供します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>  
class CRowset  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 アクセサー クラス。 既定値は、`CAccessorBase` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/crowset-addrefrows.md)|現在の行に関連付けられている参照カウントをインクリメントします。|  
|[閉じる](../../data/oledb/crowset-close.md)|行と、現在のリリース`IRowset`インターフェイスです。|  
|[Compare](../../data/oledb/crowset-compare.md)|使用してをブックマーク 2 つの比較[IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx)です。|  
|[CRowset](../../data/oledb/crowset-crowset.md)|新たに作成`CRowset`オブジェクトおよび (必要に応じて) に関連付けます、 **IRowset**インターフェイスのパラメーターとして指定します。|  
|[削除](../../data/oledb/crowset-delete.md)|使用して、行セットから行を削除[IRowsetChange:DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx)です。|  
|[FindNextRow](../../data/oledb/crowset-findnextrow.md)|指定されたブックマーク後、次の一致する行を検索します。|  
|[GetApproximatePosition](../../data/oledb/crowset-getapproximateposition.md)|ブックマークに対応する行のおおよその位置を返します。|  
|[GetData](../../data/oledb/crowset-getdata.md)|行の行セットのコピーからデータを取得します。|  
|[GetDataHere](../../data/oledb/crowset-getdatahere.md)|指定したバッファーからデータを取得します。|  
|[GetOriginalData](../../data/oledb/crowset-getoriginaldata.md)|最近からフェッチまたは保留中の変更を無視して、データ ソースに送信されるデータを取得します。|  
|[GetRowStatus](../../data/oledb/crowset-getrowstatus.md)|すべての行の状態を返します。|  
|[[挿入]](../../data/oledb/crowset-insert.md)|作成して使用して新しい行を挿入[IRowsetChange:InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx)です。|  
|[IsSameRow](../../data/oledb/crowset-issamerow.md)|指定された行を現在の行とを比較します。|  
|[MoveFirst](../../data/oledb/crowset-movefirst.md)|次のフェッチ位置の初期位置に移動します。|  
|[MoveLast](../../data/oledb/crowset-movelast.md)|最後のレコードに移動します。|  
|[MoveNext](../../data/oledb/crowset-movenext.md)|[次へ] の順次行または、指定した数の次の行を超える位置からのデータをフェッチします。|  
|[MovePrev](../../data/oledb/crowset-moveprev.md)|前のレコードに移動します。|  
|[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)|そのブックマークからのブックマークでマークされた行または指定されたオフセット位置の行をフェッチします。|  
|[MoveToRatio](../../data/oledb/crowset-movetoratio.md)|行セット内の小数部の位置から始まる行がフェッチされます。|  
|[ReleaseRows](../../data/oledb/crowset-releaserows.md)|呼び出し[irowset::releaserows](https://msdn.microsoft.com/en-us/library/ms719771.aspx)を現在の行ハンドルを解放します。|  
|[SetData](../../data/oledb/crowset-setdata.md)|使用して行の 1 つまたは複数の列のデータ値を設定[IRowsetChange:SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx)です。|  
|[元に戻す](../../data/oledb/crowset-undo.md)|最後のフェッチ行に加えられた変更を元に戻すまたは[更新](../../data/oledb/crowset-update.md)です。|  
|[更新](../../data/oledb/crowset-update.md)|保留中の最後のフェッチまたは更新してから、現在の行に加えられた変更を送信します。|  
|[UpdateAll](../../data/oledb/crowset-updateall.md)|保留中の最後のフェッチまたは更新プログラム以降のすべての行に行われた変更を送信します。|  
  
## <a name="remarks"></a>コメント  
 OLE db では、行セットは、使用するプログラムが設定し、データの取得オブジェクトです。  
  
 このクラスがインスタンス化されるが、テンプレート パラメーターとしてではなく渡されたものではありません`CTable`または`CCommand`(`CRowset`既定値です)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [DBViewer サンプル](../../visual-cpp-samples.md)   
 [MultiRead サンプル](../../visual-cpp-samples.md)   
 [MultiRead 属性サンプル](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)