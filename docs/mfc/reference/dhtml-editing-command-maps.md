---
title: DHTML 編集コマンド マップ
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: f4bbfb500e8de9594bbaa334b4e227caeaa845da
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837412"
---
# <a name="dhtml-editing-command-maps"></a>DHTML 編集コマンド マップ

次のマクロは、 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)派生クラスで DHTML 編集コマンドをマップするために使用できます。 使用例については、「 [HTMLEdit Sample](../../overview/visual-cpp-samples.md)」を参照してください。

### <a name="dhtml-editing-command-map-macros"></a>DHTML 編集コマンドマップマクロ

|名前|説明|
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|クラスで DHTML 編集コマンドマップを宣言します。|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|クラス内で DHTML 編集コマンドマップの定義を開始します。|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML 編集コマンドマップの末尾をマークします。|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|コマンド ID を HTML 編集コマンドにマップします。|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|コマンド ID を HTML 編集コマンドとメッセージハンドラーにマップします。|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|コマンド ID を HTML 編集コマンドとユーザーインターフェイス要素にマップします。|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|コマンド ID を HTML 編集コマンド、メッセージハンドラー、およびユーザーインターフェイス要素にマップします。|

## <a name="declare_dhtmlediting_cmdmap"></a><a name="declare_dhtmlediting_cmdmap"></a> DECLARE_DHTMLEDITING_CMDMAP

クラスで DHTML 編集コマンドマップを宣言します。

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
クラスの名前。

### <a name="remarks"></a>解説

このマクロは、 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)派生クラスの定義で使用されます。

[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)を使用してマップを実装します。

### <a name="example"></a>例

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml. h

## <a name="begin_dhtmlediting_cmdmap"></a><a name="begin_dhtmlediting_cmdmap"></a> BEGIN_DHTMLEDITING_CMDMAP

クラス内で DHTML 編集コマンドマップの定義を開始します。

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
DHTML 編集コマンドマップを格納しているクラスの名前。 このクラスは、 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) から直接または間接的に派生し、そのクラス定義内に [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) マクロを含める必要があります。

### <a name="remarks"></a>解説

ユーザーインターフェイスコマンドを HTML 編集コマンドにマップするには、クラスに DHTML 編集コマンドマップを追加します。

クラスの実装 (.cpp) ファイルに BEGIN_DHTMLEDITING_CMDMAP マクロを配置した後、クラスがマップするコマンド (たとえば、ID_EDIT_CUT から IDM_CUT) に対してマクロを [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) します。 [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)マクロを使用して、イベントマップの終了をマークします。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml. h

## <a name="end_dhtmlediting_cmdmap"></a><a name="end_dhtmlediting_cmdmap"></a> END_DHTMLEDITING_CMDMAP

DHTML 編集コマンドマップの末尾をマークします。

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>解説

[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)と組み合わせて使用します。

### <a name="example"></a>例

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml. h

## <a name="dhtmlediting_cmd_entry"></a><a name="dhtmlediting_cmd_entry"></a> DHTMLEDITING_CMD_ENTRY

コマンド ID を HTML 編集コマンドにマップします。

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID (ID_EDIT_COPY など)。

*dhtmlcmdID*<br/>
*CmdID*マップ (IDM_COPY など) の対象となる HTML 編集コマンド。

### <a name="example"></a>例

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml. h

## <a name="dhtmlediting_cmd_entry_func"></a><a name="dhtmlediting_cmd_entry_func"></a> DHTMLEDITING_CMD_ENTRY_FUNC

コマンド ID を HTML 編集コマンドとメッセージハンドラーにマップします。

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID (ID_EDIT_COPY など)。

*dhtmlcmdID*<br/>
*CmdID*マップ (IDM_COPY など) の対象となる HTML 編集コマンド。

*member_func_name*<br/>
コマンドのマップ先となるメッセージハンドラー関数の名前。

### <a name="example"></a>例

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml. h

## <a name="dhtmlediting_cmd_entry_type"></a><a name="dhtmlediting_cmd_entry_type"></a> DHTMLEDITING_CMD_ENTRY_TYPE

コマンド ID を HTML 編集コマンドとユーザーインターフェイス要素にマップします。

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID (ID_EDIT_COPY など)。

*dhtmlcmdID*<br/>
*CmdID*マップ (IDM_COPY など) の対象となる HTML 編集コマンド。

*型の種類*<br/>
ユーザーインターフェイス要素の型。AFX_UI_ELEMTYPE_NORMAL、AFX_UI_ELEMTYPE_CHECKBOX、または AFX_UI_ELEMTYPE_RADIO のいずれか。

### <a name="example"></a>例

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml. h

## <a name="dhtmlediting_cmd_entry_func_type"></a><a name="dhtmlediting_cmd_entry_func_type"></a> DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

コマンド ID を HTML 編集コマンド、メッセージハンドラー、およびユーザーインターフェイス要素にマップします。

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID (ID_EDIT_COPY など)。

*dhtmlcmdID*<br/>
*CmdID*マップ (IDM_COPY など) の対象となる HTML 編集コマンド。

*member_func_name*<br/>
コマンドのマップ先となるメッセージハンドラー関数の名前。

*型の種類*<br/>
ユーザーインターフェイス要素の型。AFX_UI_ELEMTYPE_NORMAL、AFX_UI_ELEMTYPE_CHECKBOX、または AFX_UI_ELEMTYPE_RADIO のいずれか。

### <a name="example"></a>例

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxhtml. h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
