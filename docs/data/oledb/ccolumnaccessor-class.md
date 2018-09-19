---
title: CColumnAccessor クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs:
- C++
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b1843b6279cb7c86762cc6d975a2a7e67d3d278d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055638"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor クラス

挿入されたコンシューマー コードを生成します。  
  
## <a name="syntax"></a>構文

```cpp
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Remarks  

挿入されたコードを別のアクセサーとして、すべての列がバインドされています。 挿入されたコードでこのクラスを使用することに注意する必要が (たとえば、発生する可能性がこれをデバッグするとき) が、通常しないか、そのメソッドを直接使用します。  
  
`CColumnAccessor` その他のアクセサー クラスのメソッドの機能で対応の次のスタブ メソッドを実装します。  
  
- `CColumnAccessor` コンス トラクター。インスタンスを作成し、初期化、`CColumnAccessor`オブジェクト。  
  
- `CreateAccessor` 列バインド構造体のメモリを割り当て、列のデータ メンバーを初期化します。  
  
- `BindColumns` アクセサーには、列をバインドします。  
  
- `SetParameterBuffer` パラメーターのバッファーを割り当てます。  
  
- `AddParameter` パラメーターのエントリの構造体には、パラメーターの入力を追加します。  
  
- `HasOutputColumns` アクセサーに出力列があるかどうかを決定します。  
  
- `HasParameters` アクセサーがパラメーターを持つかどうかを判断します。  
  
- `BindParameters` 列に作成されたパラメーターをバインドします。  
  
## <a name="requirements"></a>要件  

**ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)