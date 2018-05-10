---
title: DHTML 編集コマンド マップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69630d00b09534d97d5e46a8400b73f0e9d85b24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dhtml-editing-command-maps"></a>DHTML 編集コマンド マップ
DHTML 編集コマンドをマップに次のマクロを使用できる[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-クラスを派生します。 それらの使用例は、次を参照してください。 [HTMLEdit サンプル](../../visual-cpp-samples.md)です。  
  
### <a name="dhtml-editing-command-map-macros"></a>DHTML 編集コマンド マップ マクロ  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|クラスで DHTML 編集コマンド マップを宣言します。|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|DHTML 編集コマンド マップ、クラス内での定義を開始します。|  
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML 編集コマンド マップの最後をマークします。|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|HTML 編集コマンドをコマンド ID を割り当てます。|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|コマンド ID を HTML 編集コマンドとメッセージ ハンドラーにマップします。|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|HTML 編集コマンドとユーザー インターフェイス要素にコマンド ID を割り当てます。|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|HTML コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素を編集するには、コマンド ID を割り当てます。|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP  
 クラスで DHTML 編集コマンド マップを宣言します。  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 クラスの名前。  
  
### <a name="remarks"></a>コメント  
 このマクロの定義で使用するのには、 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-クラスを派生します。  
  
 使用して[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)マップを実装します。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP  
 DHTML 編集コマンド マップ、クラス内での定義を開始します。  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 DHTML 編集コマンド マップを含むクラスの名前です。 このクラスから直接または間接的を派生する必要があります[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)を含めると、 [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)そのクラス定義内でのマクロです。  
  
### <a name="remarks"></a>コメント  
 DHTML 編集コマンド マップは、ユーザー インターフェイスのコマンドを HTML の編集コマンドにマップするクラスに追加します。  
  
 場所、`BEGIN_DHTMLEDITING_CMDMAP`クラスの実装 (.cpp) ファイル内のマクロが続く[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)にマップするクラスは、コマンドのマクロ (からの変更など、 **ID_EDIT_CUT** に**IDM_CUT**)。 使用して、 [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)マクロ イベント マップの終わりをマークします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP  
 DHTML 編集コマンド マップの最後をマークします。  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用して[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)です。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY  
 HTML 編集コマンドをコマンド ID を割り当てます。  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (など**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (など**IDM_COPY**)。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC  
 コマンド ID を HTML 編集コマンドとメッセージ ハンドラーにマップします。  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (など**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (など**IDM_COPY**)。  
  
 `member_func_name`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE  
 HTML 編集コマンドとユーザー インターフェイス要素にコマンド ID を割り当てます。  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (など**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (など**IDM_COPY**)。  
  
 `elemType`  
 ユーザー インターフェイス要素の型です。いずれかの**AFX_UI_ELEMTYPE_NORMAL**、 **AFX_UI_ELEMTYPE_CHECKBOX**、または**AFX_UI_ELEMTYPE_RADIO**です。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 HTML コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素を編集するには、コマンド ID を割り当てます。  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (など**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (など**IDM_COPY**)。  
  
 `member_func_name`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
 `elemType`  
 ユーザー インターフェイス要素の型です。いずれかの**AFX_UI_ELEMTYPE_NORMAL**、 **AFX_UI_ELEMTYPE_CHECKBOX**、または**AFX_UI_ELEMTYPE_RADIO**です。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)です。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
