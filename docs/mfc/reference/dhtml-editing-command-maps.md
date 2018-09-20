---
title: DHTML 編集コマンド マップ |Microsoft Docs
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
ms.openlocfilehash: e31490f62c170230c41a2a2a26fcbe116d39d415
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425068"
---
# <a name="dhtml-editing-command-maps"></a>DHTML 編集コマンド マップ

DHTML 編集コマンド マップに次のマクロを使用できる[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-クラスを派生します。 使用の例は、次を参照してください。 [HTMLEdit サンプル](../../visual-cpp-samples.md)します。

### <a name="dhtml-editing-command-map-macros"></a>DHTML 編集コマンド マップ マクロ

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|DHTML 編集コマンド マップ クラスで宣言します。|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|DHTML 編集コマンド マップ、クラス内での定義を開始します。|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML 編集コマンド マップの末尾をマークします。|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|HTML の編集コマンドをコマンド ID をマップします。|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|HTML 編集コマンドとメッセージ ハンドラーには、コマンド ID を割り当てます。|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|HTML 編集コマンドとユーザー インターフェイス要素には、コマンド ID を割り当てます。|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|HTML コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素を編集するには、コマンド ID をマップします。|

##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP

DHTML 編集コマンド マップ クラスで宣言します。

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
クラスの名前。

### <a name="remarks"></a>Remarks

このマクロは、の定義で使用される[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-クラスを派生します。

使用[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)マップを実装します。

### <a name="example"></a>例

参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。

### <a name="requirements"></a>要件

  **ヘッダー** afxhtml.h

##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP

DHTML 編集コマンド マップ、クラス内での定義を開始します。

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
DHTML 編集コマンド マップを含むクラスの名前。 このクラスから直接または間接的に派生する必要があります[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)を含めると、 [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)マクロをそのクラス定義内で。

### <a name="remarks"></a>Remarks

DHTML 編集コマンド マップは、ユーザー インターフェイスのコマンドを HTML の編集コマンドにマップするクラスに追加します。

BEGIN_DHTMLEDITING_CMDMAP マクロに続く、クラスの実装 (.cpp) ファイルに配置[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)クラスは、(たとえば、IDM_CUT に ID_EDIT_CUT) からマップするコマンドのマクロ。 使用して、 [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)マクロ イベント マップの終わりをマークします。

### <a name="requirements"></a>要件

  **ヘッダー** afxhtml.h

##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP

DHTML 編集コマンド マップの末尾をマークします。

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Remarks

組み合わせて使用[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)します。

### <a name="example"></a>例

参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。

### <a name="requirements"></a>要件

  **ヘッダー** afxhtml.h

##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY

HTML の編集コマンドをコマンド ID をマップします。

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
ID_EDIT_COPY) などのコマンド ID。

*dhtmlcmdID*<br/>
編集コマンドを HTML *cmdID* (IDM_COPY) などにマップします。

### <a name="example"></a>例

参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。

### <a name="requirements"></a>要件

  **ヘッダー** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC

HTML 編集コマンドとメッセージ ハンドラーには、コマンド ID を割り当てます。

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
ID_EDIT_COPY) などのコマンド ID。

*dhtmlcmdID*<br/>
編集コマンドを HTML *cmdID* (IDM_COPY) などにマップします。

*member_func_name*<br/>
コマンドがマップされているメッセージ ハンドラー関数の名前。

### <a name="example"></a>例

参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。

### <a name="requirements"></a>要件

  **ヘッダー** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE

HTML 編集コマンドとユーザー インターフェイス要素には、コマンド ID を割り当てます。

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
ID_EDIT_COPY) などのコマンド ID。

*dhtmlcmdID*<br/>
編集コマンドを HTML *cmdID* (IDM_COPY) などにマップします。

*elemType*<br/>
ユーザー インターフェイス要素の型。AFX_UI_ELEMTYPE_NORMAL、AFX_UI_ELEMTYPE_CHECKBOX、AFX_UI_ELEMTYPE_RADIO のいずれか。

### <a name="example"></a>例

参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。

### <a name="requirements"></a>要件

  **ヘッダー** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

HTML コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素を編集するには、コマンド ID をマップします。

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
ID_EDIT_COPY) などのコマンド ID。

*dhtmlcmdID*<br/>
編集コマンドを HTML *cmdID* (IDM_COPY) などにマップします。

*member_func_name*<br/>
コマンドがマップされているメッセージ ハンドラー関数の名前。

*elemType*<br/>
ユーザー インターフェイス要素の型。AFX_UI_ELEMTYPE_NORMAL、AFX_UI_ELEMTYPE_CHECKBOX、AFX_UI_ELEMTYPE_RADIO のいずれか。

### <a name="example"></a>例

参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。

### <a name="requirements"></a>要件

  **ヘッダー** afxhtml.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
