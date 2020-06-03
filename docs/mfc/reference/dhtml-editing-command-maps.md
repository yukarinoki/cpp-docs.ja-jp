---
title: DHTML 編集コマンド マップ
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: 62b388eb178be018655ea2b2be00d7321da50335
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365817"
---
# <a name="dhtml-editing-command-maps"></a>DHTML 編集コマンド マップ

次のマクロを使用して[、CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-派生クラスの DHTML 編集コマンドをマップできます。 その使用例については[、「HTML 編集のサンプル](../../overview/visual-cpp-samples.md)」を参照してください。

### <a name="dhtml-editing-command-map-macros"></a>DHTML 編集コマンド マップ マクロ

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|DHTML 編集コマンド マップをクラスで宣言します。|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|クラス内の DHTML 編集コマンド マップの定義を開始します。|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML 編集コマンド マップの末尾をマークします。|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|コマンド ID を HTML 編集コマンドにマップします。|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|コマンド ID を HTML 編集コマンドおよびメッセージ ハンドラーに割り当てます。|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|コマンド ID を HTML 編集コマンドおよびユーザー インターフェイス要素に割り当てる。|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|コマンド ID を HTML 編集コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素に割り当てます。|

## <a name="declare_dhtmlediting_cmdmap"></a><a name="declare_dhtmlediting_cmdmap"></a>DECLARE_DHTMLEDITING_CMDMAP

DHTML 編集コマンド マップをクラスで宣言します。

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
クラスの名前。

### <a name="remarks"></a>解説

このマクロは[、CHtmlEditView](../../mfc/reference/chtmleditview-class.md)派生クラスの定義で使用されます。

[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)を使用してマップを実装します。

### <a name="example"></a>例

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml.h

## <a name="begin_dhtmlediting_cmdmap"></a><a name="begin_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP

クラス内の DHTML 編集コマンド マップの定義を開始します。

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
DHTML 編集コマンド マップを含むクラスの名前。 このクラスは、直接または間接的に[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)から派生し、そのクラス定義内に[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)マクロを含める必要があります。

### <a name="remarks"></a>解説

クラスに DHTML 編集コマンド マップを追加して、ユーザー インターフェイス コマンドを HTML 編集コマンドにマップします。

BEGIN_DHTMLEDITING_CMDMAPマクロをクラスの実装 (.cpp) ファイルに置き、その後にクラスがマップするコマンド (ID_EDIT_CUT からIDM_CUTなど) のマクロを[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)します。 [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)マクロを使用して、イベント マップの終了をマークします。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml.h

## <a name="end_dhtmlediting_cmdmap"></a><a name="end_dhtmlediting_cmdmap"></a>END_DHTMLEDITING_CMDMAP

DHTML 編集コマンド マップの末尾をマークします。

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>解説

[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)と組み合わせて使用します。

### <a name="example"></a>例

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml.h

## <a name="dhtmlediting_cmd_entry"></a><a name="dhtmlediting_cmd_entry"></a>DHTMLEDITING_CMD_ENTRY

コマンド ID を HTML 編集コマンドにマップします。

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID (ID_EDIT_COPYなど)。

*を使用します。*<br/>
*cmdID*がマップする HTML 編集コマンド (IDM_COPYなど)。

### <a name="example"></a>例

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func"></a><a name="dhtmlediting_cmd_entry_func"></a>DHTMLEDITING_CMD_ENTRY_FUNC

コマンド ID を HTML 編集コマンドおよびメッセージ ハンドラーに割り当てます。

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID (ID_EDIT_COPYなど)。

*を使用します。*<br/>
*cmdID*がマップする HTML 編集コマンド (IDM_COPYなど)。

*member_func_name*<br/>
コマンドがマップされるメッセージ ハンドラー関数の名前。

### <a name="example"></a>例

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml.h

## <a name="dhtmlediting_cmd_entry_type"></a><a name="dhtmlediting_cmd_entry_type"></a>DHTMLEDITING_CMD_ENTRY_TYPE

コマンド ID を HTML 編集コマンドおよびユーザー インターフェイス要素に割り当てる。

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID (ID_EDIT_COPYなど)。

*を使用します。*<br/>
*cmdID*がマップする HTML 編集コマンド (IDM_COPYなど)。

*エレムタイプ*<br/>
ユーザー インターフェイス要素の型。AFX_UI_ELEMTYPE_NORMAL、AFX_UI_ELEMTYPE_CHECKBOX、またはAFX_UI_ELEMTYPE_RADIOのいずれか。

### <a name="example"></a>例

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func_type"></a><a name="dhtmlediting_cmd_entry_func_type"></a>DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

コマンド ID を HTML 編集コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素に割り当てます。

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID (ID_EDIT_COPYなど)。

*を使用します。*<br/>
*cmdID*がマップする HTML 編集コマンド (IDM_COPYなど)。

*member_func_name*<br/>
コマンドがマップされるメッセージ ハンドラー関数の名前。

*エレムタイプ*<br/>
ユーザー インターフェイス要素の型。AFX_UI_ELEMTYPE_NORMAL、AFX_UI_ELEMTYPE_CHECKBOX、またはAFX_UI_ELEMTYPE_RADIOのいずれか。

### <a name="example"></a>例

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
