---
title: DEFINE_COMMAND_EX |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND_EX
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b2a77fa0d6655edeee88df3c7c45e1936a766b40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
使用する場合、行セットの作成に使用されるコマンドを指定、 [CCommand](../../data/oledb/ccommand-class.md)クラスです。 Unicode と ANSI のアプリケーションをサポートしています。  
  
## <a name="syntax"></a>構文  
  
```cpp
DEFINE_COMMAND_EX(x, wszCommand)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *x*  
 [in]ユーザー レコード (コマンド) クラスの名前。  
  
 `wszCommand`  
 [in]使用する場合、行セットの作成に使用されるコマンド文字列[CCommand](../../data/oledb/ccommand-class.md)です。  
  
## <a name="remarks"></a>コメント  
 コマンド文字列を指定するには、コマンド テキストを指定しない場合は、既定値として使用されます、 [ccommand::open](../../data/oledb/ccommand-open.md)メソッドです。  
  
 このマクロは、アプリケーションの種類に関係なく、Unicode 文字列を受け取ります。 このマクロは優先[DEFINE_COMMAND](../../data/oledb/define-command.md) Unicode をサポートするための ANSI アプリケーションだけでなくです。  
  
## <a name="example"></a>例  
 参照してください[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)