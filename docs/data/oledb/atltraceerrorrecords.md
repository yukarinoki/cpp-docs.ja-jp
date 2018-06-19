---
title: AtlTraceErrorRecords |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afea3c3ef1f169e5f1cb5fc675c74b54da1be0d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093348"
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
エラーが返された場合は、ダンプ デバイスに OLE DB エラー レコード情報をダンプします。  
  
## <a name="syntax"></a>構文  
  
```cpp
      inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hErr`  
 [in]`HRESULT` OLE DB コンシューマー テンプレート メンバー関数によって返されます。  
  
## <a name="remarks"></a>コメント  
 場合`hErr`は`S_OK`、`AtlTraceErrorRecords`ダンプの OLE DB エラー レコード情報をダンプ デバイス (、**デバッグ**ファイルまたは出力ウィンドウのタブ)。 エラー レコードについてには、プロバイダーから取得されるには、各エラー レコード エントリの行番号、ソース、説明、ヘルプ ファイルをコンテキスト、および GUID が含まれます。 `AtlTraceErrorRecords` デバッグ ビルドでのみこの情報をダンプします。 リリース ビルドでは、out に最適化された空のスタブを勧めします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)