---
title: DEFINE_COMMAND |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND macro
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51f975b0477d29fbb35880c796f52612456c32c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="definecommand"></a>DEFINE_COMMAND
使用する場合、行セットの作成に使用されるコマンドを指定、 [CCommand](../../data/oledb/ccommand-class.md)クラスです。 指定したアプリケーションの種類 (ANSI または Unicode) に対応する文字列型のみを受け入れます。  
  
> [!NOTE]
>  使用することをお勧め[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)の代わりに`DEFINE_COMMAND`です。  
  
## <a name="syntax"></a>構文  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *x*  
 [in]ユーザー レコード (コマンド) クラスの名前。  
  
 `szCommand`  
 [in]使用する場合、行セットの作成に使用されるコマンド文字列[CCommand](../../data/oledb/ccommand-class.md)です。  
  
## <a name="remarks"></a>コメント  
 コマンド文字列を指定するには、コマンド テキストを指定しない場合は、既定値として使用されます、 [ccommand::open](../../data/oledb/ccommand-open.md)メソッドです。  
  
 このマクロは、Unicode としてアプリケーションをビルドする場合、ANSI、として、アプリケーションをビルドする場合の ANSI 文字列または Unicode 文字列を受け取ります。 使用することをお勧め[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)の代わりに`DEFINE_COMMAND`前者は ANSI または Unicode アプリケーションの種類に関係なく、Unicode 文字列を受け付けるため、します。  
  
## <a name="example"></a>例  
 参照してください[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)