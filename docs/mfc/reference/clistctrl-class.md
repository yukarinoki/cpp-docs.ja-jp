---
title: CListCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CListCtrl
- AFXCMN/CListCtrl
- AFXCMN/CListCtrl::CListCtrl
- AFXCMN/CListCtrl::ApproximateViewRect
- AFXCMN/CListCtrl::Arrange
- AFXCMN/CListCtrl::CancelEditLabel
- AFXCMN/CListCtrl::Create
- AFXCMN/CListCtrl::CreateDragImage
- AFXCMN/CListCtrl::CreateEx
- AFXCMN/CListCtrl::DeleteAllItems
- AFXCMN/CListCtrl::DeleteColumn
- AFXCMN/CListCtrl::DeleteItem
- AFXCMN/CListCtrl::DrawItem
- AFXCMN/CListCtrl::EditLabel
- AFXCMN/CListCtrl::EnableGroupView
- AFXCMN/CListCtrl::EnsureVisible
- AFXCMN/CListCtrl::FindItem
- AFXCMN/CListCtrl::GetBkColor
- AFXCMN/CListCtrl::GetBkImage
- AFXCMN/CListCtrl::GetCallbackMask
- AFXCMN/CListCtrl::GetCheck
- AFXCMN/CListCtrl::GetColumn
- AFXCMN/CListCtrl::GetColumnOrderArray
- AFXCMN/CListCtrl::GetColumnWidth
- AFXCMN/CListCtrl::GetCountPerPage
- AFXCMN/CListCtrl::GetEditControl
- AFXCMN/CListCtrl::GetEmptyText
- AFXCMN/CListCtrl::GetExtendedStyle
- AFXCMN/CListCtrl::GetFirstSelectedItemPosition
- AFXCMN/CListCtrl::GetFocusedGroup
- AFXCMN/CListCtrl::GetGroupCount
- AFXCMN/CListCtrl::GetGroupInfo
- AFXCMN/CListCtrl::GetGroupInfoByIndex
- AFXCMN/CListCtrl::GetGroupMetrics
- AFXCMN/CListCtrl::GetGroupRect
- AFXCMN/CListCtrl::GetGroupState
- AFXCMN/CListCtrl::GetHeaderCtrl
- AFXCMN/CListCtrl::GetHotCursor
- AFXCMN/CListCtrl::GetHotItem
- AFXCMN/CListCtrl::GetHoverTime
- AFXCMN/CListCtrl::GetImageList
- AFXCMN/CListCtrl::GetInsertMark
- AFXCMN/CListCtrl::GetInsertMarkColor
- AFXCMN/CListCtrl::GetInsertMarkRect
- AFXCMN/CListCtrl::GetItem
- AFXCMN/CListCtrl::GetItemCount
- AFXCMN/CListCtrl::GetItemData
- AFXCMN/CListCtrl::GetItemIndexRect
- AFXCMN/CListCtrl::GetItemPosition
- AFXCMN/CListCtrl::GetItemRect
- AFXCMN/CListCtrl::GetItemSpacing
- AFXCMN/CListCtrl::GetItemState
- AFXCMN/CListCtrl::GetItemText
- AFXCMN/CListCtrl::GetNextItem
- AFXCMN/CListCtrl::GetNextItemIndex
- AFXCMN/CListCtrl::GetNextSelectedItem
- AFXCMN/CListCtrl::GetNumberOfWorkAreas
- AFXCMN/CListCtrl::GetOrigin
- AFXCMN/CListCtrl::GetOutlineColor
- AFXCMN/CListCtrl::GetSelectedColumn
- AFXCMN/CListCtrl::GetSelectedCount
- AFXCMN/CListCtrl::GetSelectionMark
- AFXCMN/CListCtrl::GetStringWidth
- AFXCMN/CListCtrl::GetSubItemRect
- AFXCMN/CListCtrl::GetTextBkColor
- AFXCMN/CListCtrl::GetTextColor
- AFXCMN/CListCtrl::GetTileInfo
- AFXCMN/CListCtrl::GetTileViewInfo
- AFXCMN/CListCtrl::GetToolTips
- AFXCMN/CListCtrl::GetTopIndex
- AFXCMN/CListCtrl::GetView
- AFXCMN/CListCtrl::GetViewRect
- AFXCMN/CListCtrl::GetWorkAreas
- AFXCMN/CListCtrl::HasGroup
- AFXCMN/CListCtrl::HitTest
- AFXCMN/CListCtrl::InsertColumn
- AFXCMN/CListCtrl::InsertGroup
- AFXCMN/CListCtrl::InsertGroupSorted
- AFXCMN/CListCtrl::InsertItem
- AFXCMN/CListCtrl::InsertMarkHitTest
- AFXCMN/CListCtrl::IsGroupViewEnabled
- AFXCMN/CListCtrl::IsItemVisible
- AFXCMN/CListCtrl::MapIDToIndex
- AFXCMN/CListCtrl::MapIndexToID
- AFXCMN/CListCtrl::MoveGroup
- AFXCMN/CListCtrl::MoveItemToGroup
- AFXCMN/CListCtrl::RedrawItems
- AFXCMN/CListCtrl::RemoveAllGroups
- AFXCMN/CListCtrl::RemoveGroup
- AFXCMN/CListCtrl::Scroll
- AFXCMN/CListCtrl::SetBkColor
- AFXCMN/CListCtrl::SetBkImage
- AFXCMN/CListCtrl::SetCallbackMask
- AFXCMN/CListCtrl::SetCheck
- AFXCMN/CListCtrl::SetColumn
- AFXCMN/CListCtrl::SetColumnOrderArray
- AFXCMN/CListCtrl::SetColumnWidth
- AFXCMN/CListCtrl::SetExtendedStyle
- AFXCMN/CListCtrl::SetGroupInfo
- AFXCMN/CListCtrl::SetGroupMetrics
- AFXCMN/CListCtrl::SetHotCursor
- AFXCMN/CListCtrl::SetHotItem
- AFXCMN/CListCtrl::SetHoverTime
- AFXCMN/CListCtrl::SetIconSpacing
- AFXCMN/CListCtrl::SetImageList
- AFXCMN/CListCtrl::SetInfoTip
- AFXCMN/CListCtrl::SetInsertMark
- AFXCMN/CListCtrl::SetInsertMarkColor
- AFXCMN/CListCtrl::SetItem
- AFXCMN/CListCtrl::SetItemCount
- AFXCMN/CListCtrl::SetItemCountEx
- AFXCMN/CListCtrl::SetItemData
- AFXCMN/CListCtrl::SetItemIndexState
- AFXCMN/CListCtrl::SetItemPosition
- AFXCMN/CListCtrl::SetItemState
- AFXCMN/CListCtrl::SetItemText
- AFXCMN/CListCtrl::SetOutlineColor
- AFXCMN/CListCtrl::SetSelectedColumn
- AFXCMN/CListCtrl::SetSelectionMark
- AFXCMN/CListCtrl::SetTextBkColor
- AFXCMN/CListCtrl::SetTextColor
- AFXCMN/CListCtrl::SetTileInfo
- AFXCMN/CListCtrl::SetTileViewInfo
- AFXCMN/CListCtrl::SetToolTips
- AFXCMN/CListCtrl::SetView
- AFXCMN/CListCtrl::SetWorkAreas
- AFXCMN/CListCtrl::SortGroups
- AFXCMN/CListCtrl::SortItems
- AFXCMN/CListCtrl::SortItemsEx
- AFXCMN/CListCtrl::SubItemHitTest
- AFXCMN/CListCtrl::Update
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl [MFC], CListCtrl
- CListCtrl [MFC], ApproximateViewRect
- CListCtrl [MFC], Arrange
- CListCtrl [MFC], CancelEditLabel
- CListCtrl [MFC], Create
- CListCtrl [MFC], CreateDragImage
- CListCtrl [MFC], CreateEx
- CListCtrl [MFC], DeleteAllItems
- CListCtrl [MFC], DeleteColumn
- CListCtrl [MFC], DeleteItem
- CListCtrl [MFC], DrawItem
- CListCtrl [MFC], EditLabel
- CListCtrl [MFC], EnableGroupView
- CListCtrl [MFC], EnsureVisible
- CListCtrl [MFC], FindItem
- CListCtrl [MFC], GetBkColor
- CListCtrl [MFC], GetBkImage
- CListCtrl [MFC], GetCallbackMask
- CListCtrl [MFC], GetCheck
- CListCtrl [MFC], GetColumn
- CListCtrl [MFC], GetColumnOrderArray
- CListCtrl [MFC], GetColumnWidth
- CListCtrl [MFC], GetCountPerPage
- CListCtrl [MFC], GetEditControl
- CListCtrl [MFC], GetEmptyText
- CListCtrl [MFC], GetExtendedStyle
- CListCtrl [MFC], GetFirstSelectedItemPosition
- CListCtrl [MFC], GetFocusedGroup
- CListCtrl [MFC], GetGroupCount
- CListCtrl [MFC], GetGroupInfo
- CListCtrl [MFC], GetGroupInfoByIndex
- CListCtrl [MFC], GetGroupMetrics
- CListCtrl [MFC], GetGroupRect
- CListCtrl [MFC], GetGroupState
- CListCtrl [MFC], GetHeaderCtrl
- CListCtrl [MFC], GetHotCursor
- CListCtrl [MFC], GetHotItem
- CListCtrl [MFC], GetHoverTime
- CListCtrl [MFC], GetImageList
- CListCtrl [MFC], GetInsertMark
- CListCtrl [MFC], GetInsertMarkColor
- CListCtrl [MFC], GetInsertMarkRect
- CListCtrl [MFC], GetItem
- CListCtrl [MFC], GetItemCount
- CListCtrl [MFC], GetItemData
- CListCtrl [MFC], GetItemIndexRect
- CListCtrl [MFC], GetItemPosition
- CListCtrl [MFC], GetItemRect
- CListCtrl [MFC], GetItemSpacing
- CListCtrl [MFC], GetItemState
- CListCtrl [MFC], GetItemText
- CListCtrl [MFC], GetNextItem
- CListCtrl [MFC], GetNextItemIndex
- CListCtrl [MFC], GetNextSelectedItem
- CListCtrl [MFC], GetNumberOfWorkAreas
- CListCtrl [MFC], GetOrigin
- CListCtrl [MFC], GetOutlineColor
- CListCtrl [MFC], GetSelectedColumn
- CListCtrl [MFC], GetSelectedCount
- CListCtrl [MFC], GetSelectionMark
- CListCtrl [MFC], GetStringWidth
- CListCtrl [MFC], GetSubItemRect
- CListCtrl [MFC], GetTextBkColor
- CListCtrl [MFC], GetTextColor
- CListCtrl [MFC], GetTileInfo
- CListCtrl [MFC], GetTileViewInfo
- CListCtrl [MFC], GetToolTips
- CListCtrl [MFC], GetTopIndex
- CListCtrl [MFC], GetView
- CListCtrl [MFC], GetViewRect
- CListCtrl [MFC], GetWorkAreas
- CListCtrl [MFC], HasGroup
- CListCtrl [MFC], HitTest
- CListCtrl [MFC], InsertColumn
- CListCtrl [MFC], InsertGroup
- CListCtrl [MFC], InsertGroupSorted
- CListCtrl [MFC], InsertItem
- CListCtrl [MFC], InsertMarkHitTest
- CListCtrl [MFC], IsGroupViewEnabled
- CListCtrl [MFC], IsItemVisible
- CListCtrl [MFC], MapIDToIndex
- CListCtrl [MFC], MapIndexToID
- CListCtrl [MFC], MoveGroup
- CListCtrl [MFC], MoveItemToGroup
- CListCtrl [MFC], RedrawItems
- CListCtrl [MFC], RemoveAllGroups
- CListCtrl [MFC], RemoveGroup
- CListCtrl [MFC], Scroll
- CListCtrl [MFC], SetBkColor
- CListCtrl [MFC], SetBkImage
- CListCtrl [MFC], SetCallbackMask
- CListCtrl [MFC], SetCheck
- CListCtrl [MFC], SetColumn
- CListCtrl [MFC], SetColumnOrderArray
- CListCtrl [MFC], SetColumnWidth
- CListCtrl [MFC], SetExtendedStyle
- CListCtrl [MFC], SetGroupInfo
- CListCtrl [MFC], SetGroupMetrics
- CListCtrl [MFC], SetHotCursor
- CListCtrl [MFC], SetHotItem
- CListCtrl [MFC], SetHoverTime
- CListCtrl [MFC], SetIconSpacing
- CListCtrl [MFC], SetImageList
- CListCtrl [MFC], SetInfoTip
- CListCtrl [MFC], SetInsertMark
- CListCtrl [MFC], SetInsertMarkColor
- CListCtrl [MFC], SetItem
- CListCtrl [MFC], SetItemCount
- CListCtrl [MFC], SetItemCountEx
- CListCtrl [MFC], SetItemData
- CListCtrl [MFC], SetItemIndexState
- CListCtrl [MFC], SetItemPosition
- CListCtrl [MFC], SetItemState
- CListCtrl [MFC], SetItemText
- CListCtrl [MFC], SetOutlineColor
- CListCtrl [MFC], SetSelectedColumn
- CListCtrl [MFC], SetSelectionMark
- CListCtrl [MFC], SetTextBkColor
- CListCtrl [MFC], SetTextColor
- CListCtrl [MFC], SetTileInfo
- CListCtrl [MFC], SetTileViewInfo
- CListCtrl [MFC], SetToolTips
- CListCtrl [MFC], SetView
- CListCtrl [MFC], SetWorkAreas
- CListCtrl [MFC], SortGroups
- CListCtrl [MFC], SortItems
- CListCtrl [MFC], SortItemsEx
- CListCtrl [MFC], SubItemHitTest
- CListCtrl [MFC], Update
ms.assetid: fe08a1ca-4b05-4ff7-a12a-ee4c765a2197
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b44878f5b860a05029f31492a7ca8ae06d83b607
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="clistctrl-class"></a>CListCtrl クラス
"リスト ビュー コントロール" の機能をカプセル化します。このコントロールには項目のコレクションを表示され、各項目はイメージ リストのアイコンとラベルで構成されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CListCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CListCtrl::CListCtrl](#clistctrl)|`CListCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CListCtrl::ApproximateViewRect](#approximateviewrect)|幅とリスト ビュー コントロールの項目を表示するために必要な高さを決定します。|  
|[CListCtrl::Arrange](#arrange)|グリッドでアイテムを整列します。|  
|[CListCtrl::CancelEditLabel](#canceleditlabel)|項目のテキストの編集操作をキャンセルします。|  
|[CListCtrl::Create](#create)|リスト コントロールを作成し、それにアタッチ、`CListCtrl`オブジェクト。|  
|[CListCtrl::CreateDragImage](#createdragimage)|指定した項目のドラッグ イメージ リストを作成します。|  
|[CListCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してリスト コントロールを作成しにアタッチ、`CListCtrl`オブジェクト。|  
|[CListCtrl::DeleteAllItems](#deleteallitems)|コントロールからすべての項目を削除します。|  
|[CListCtrl::DeleteColumn](#deletecolumn)|リスト ビュー コントロールから列を削除します。|  
|[CListCtrl::DeleteItem](#deleteitem)|コントロールから項目を削除します。|  
|[CListCtrl::DrawItem](#drawitem)|オーナー描画コントロールの変更のビジュアルな部分ときに呼び出されます。|  
|[CListCtrl::EditLabel](#editlabel)|インプレースでのアイテムのテキストの編集を開始します。|  
|[CListCtrl::EnableGroupView](#enablegroupview)|有効またはリスト ビュー コントロール内の項目をグループとして表示するかどうかを無効にします。|  
|[CListCtrl::EnsureVisible](#ensurevisible)|項目が表示されていることを確認します。|  
|[CListCtrl::FindItem](#finditem)|指定した特性を持つリスト ビューの項目を検索します。|  
|[CListCtrl::GetBkColor](#getbkcolor)|リスト ビュー コントロールの背景色を取得します。|  
|[CListCtrl::GetBkImage](#getbkimage)|リスト ビュー コントロールの現在の背景イメージを取得します。|  
|[CListCtrl::GetCallbackMask](#getcallbackmask)|リスト ビュー コントロールのコールバック マスクを取得します。|  
|[CListCtrl::GetCheck](#getcheck)|項目に関連付けられている状態のイメージの現在の表示状態を取得します。|  
|[CListCtrl::GetColumn](#getcolumn)|コントロールの列の属性を取得します。|  
|[CListCtrl::GetColumnOrderArray](#getcolumnorderarray)|リスト ビュー コントロールの列順序 (左右から) を取得します。|  
|[CListCtrl::GetColumnWidth](#getcolumnwidth)|レポート ビューまたはリスト ビュー内の列の幅を取得します。|  
|[CListCtrl::GetCountPerPage](#getcountperpage)|リスト ビュー コントロールの垂直方向に収まる項目数を計算します。|  
|[CListCtrl::GetEditControl](#geteditcontrol)|アイテムのテキストを編集するために使用するエディット コントロールのハンドルを取得します。|  
|[CListCtrl::GetEmptyText](#getemptytext)|現在のリスト ビュー コントロールが空の場合に表示する文字列を取得します。|  
|[CListCtrl::GetExtendedStyle](#getextendedstyle)|リスト ビュー コントロールの現在の拡張スタイルを取得します。|  
|[CListCtrl::GetFirstSelectedItemPosition](#getfirstselecteditemposition)|リスト ビュー コントロール内の最初の選択のリスト ビュー項目の位置を取得します。|  
|[CListCtrl::GetFocusedGroup](#getfocusedgroup)|現在のリスト ビュー コントロールにキーボード フォーカスのあるグループを取得します。|  
|[CListCtrl::GetGroupCount](#getgroupcount)|現在のリスト ビュー コントロール内のグループの数を取得します。|  
|[CListCtrl::GetGroupInfo](#getgroupinfo)|リスト ビュー コントロールの指定されたグループの情報を取得します。|  
|[CListCtrl::GetGroupInfoByIndex](#getgroupinfobyindex)|現在のリスト ビュー コントロール内の指定されたグループに関する情報を取得します。|  
|[CListCtrl::GetGroupMetrics](#getgroupmetrics)|グループのメトリックを取得します。|  
|[CListCtrl::GetGroupRect](#getgrouprect)|現在のリスト ビュー コントロール内の指定したグループの外接する四角形を取得します。|  
|[CListCtrl::GetGroupState](#getgroupstate)|現在のリスト ビュー コントロール内の指定したグループの状態を取得します。|  
|[CListCtrl::GetHeaderCtrl](#getheaderctrl)|リスト ビュー コントロールのヘッダー コントロールを取得します。|  
|[CListCtrl::GetHotCursor](#gethotcursor)|リスト ビュー コントロールのホット トラッキングが有効になっているときに使用するカーソルを取得します。|  
|[CListCtrl::GetHotItem](#gethotitem)|カーソルの下に現在のリスト ビューの項目を取得します。|  
|[CListCtrl::GetHoverTime](#gethovertime)|リスト ビュー コントロールの現在のホバー時の時刻を取得します。|  
|[CListCtrl::GetImageList](#getimagelist)|描画のリスト ビュー項目を使用するイメージ リストのハンドルを取得します。|  
|[CListCtrl::GetInsertMark](#getinsertmark)|挿入マークの現在の位置を取得します。|  
|[CListCtrl::GetInsertMarkColor](#getinsertmarkcolor)|挿入マークの現在の色を取得します。|  
|[CListCtrl::GetInsertMarkRect](#getinsertmarkrect)|挿入ポイントの外接する四角形を取得します。|  
|[CListCtrl::GetItem](#getitem)|リスト ビュー項目の属性を取得します。|  
|[CListCtrl::GetItemCount](#getitemcount)|リスト ビュー コントロール内の項目数を取得します。|  
|[CListCtrl::GetItemData](#getitemdata)|項目に関連付けられているアプリケーション固有の値を取得します。|  
|[CListCtrl::GetItemIndexRect](#getitemindexrect)|現在のリスト ビュー コントロール内のサブアイテムの全部または一部の外接する四角形を取得します。|  
|[CListCtrl::GetItemPosition](#getitemposition)|リスト ビューの項目の位置を取得します。|  
|[CListCtrl::GetItemRect](#getitemrect)|項目の外接する四角形を取得します。|  
|[CListCtrl::GetItemSpacing](#getitemspacing)|現在のリスト ビュー コントロール内の項目間の間隔を計算します。|  
|[CListCtrl::GetItemState](#getitemstate)|リスト ビューの項目の状態を取得します。|  
|[CListCtrl::GetItemText](#getitemtext)|リスト ビューの項目またはサブ項目のテキストを取得します。|  
|[CListCtrl::GetNextItem](#getnextitem)|リスト ビューの項目と指定したプロパティと、指定した項目に指定されたリレーションシップを検索します。|  
|[CListCtrl::GetNextItemIndex](#getnextitemindex)|プロパティの指定したセットが現在のリスト ビュー コントロール内の項目のインデックスを取得します。|  
|[CListCtrl::GetNextSelectedItem](#getnextselecteditem)|リスト ビューの項目位置、および反復処理するため、選択したリスト ビュー内の [次へ] の項目の位置のインデックスを取得します。|  
|[CListCtrl::GetNumberOfWorkAreas](#getnumberofworkareas)|リスト ビュー コントロールの作業領域の現在の数を取得します。|  
|[CListCtrl::GetOrigin](#getorigin)|リスト ビュー コントロールの現在のビューの原点を取得します。|  
|[CListCtrl::GetOutlineColor](#getoutlinecolor)|リスト ビュー コントロールの境界線の色を取得します。|  
|[CListCtrl::GetSelectedColumn](#getselectedcolumn)|リスト コントロールで現在選択されている列のインデックスを取得します。|  
|[CListCtrl::GetSelectedCount](#getselectedcount)|リスト ビュー コントロールで選択した項目の数を取得します。|  
|[CListCtrl::GetSelectionMark](#getselectionmark)|リスト ビュー コントロールの選択のマークを取得します。|  
|[CListCtrl::GetStringWidth](#getstringwidth)|指定された文字列のすべてを表示するために必要な最小列幅を決定します。|  
|[CListCtrl::GetSubItemRect](#getsubitemrect)|リスト ビュー コントロール内の項目の外接する四角形を取得します。|  
|[CListCtrl::GetTextBkColor](#gettextbkcolor)|リスト ビュー コントロールのテキストの背景色を取得します。|  
|[CListCtrl::GetTextColor](#gettextcolor)|リスト ビュー コントロールのテキストの色を取得します。|  
|[CListCtrl::GetTileInfo](#gettileinfo)|リスト ビュー コントロールでのタイルに関する情報を取得します。|  
|[CListCtrl::GetTileViewInfo](#gettileviewinfo)|タイル ビューでリスト ビュー コントロールに関する情報を取得します。|  
|[CListCtrl::GetToolTips](#gettooltips)|リスト ビュー コントロールを使用してツールヒントを表示するツール ヒント コントロールを取得します。|  
|[CListCtrl::GetTopIndex](#gettopindex)|最上位に表示される項目のインデックスを取得します。|  
|[CListCtrl::GetView](#getview)|リスト ビュー コントロールのビューを取得します。|  
|[CListCtrl::GetViewRect](#getviewrect)|リスト ビュー コントロール内のすべての項目の外接する四角形を取得します。|  
|[CListCtrl::GetWorkAreas](#getworkareas)|リスト ビュー コントロールの現在の作業領域を取得します。|  
|[CListCtrl::HasGroup](#hasgroup)|リスト ビュー コントロールに、指定されたグループがあるかどうかを判断します。|  
|[CListCtrl::HitTest](#hittest)|決定するリスト ビュー項目が指定した位置にあるがします。|  
|[CListCtrl::InsertColumn](#insertcolumn)|リスト ビュー コントロールに新しい列を挿入します。|  
|[CListCtrl::InsertGroup](#insertgroup)|グループをリスト ビュー コントロールに挿入します。|  
|[CListCtrl::InsertGroupSorted](#insertgroupsorted)|グループの順序付きリストに指定されたグループを挿入します。|  
|[CListCtrl::InsertItem](#insertitem)|リスト ビュー コントロールに新しい項目を挿入します。|  
|[CListCtrl::InsertMarkHitTest](#insertmarkhittest)|指定したポイントに最も近いカーソル位置を取得します。|  
|[CListCtrl::IsGroupViewEnabled](#isgroupviewenabled)|リスト ビュー コントロールのグループの表示が有効になっているかどうかを判断します。|  
|[CListCtrl::IsItemVisible](#isitemvisible)|現在のリスト ビュー コントロール内の指定した項目を表示するかどうかを示します。|  
|[CListCtrl::MapIDToIndex](#mapidtoindex)|現在のリスト ビュー コントロール内のアイテムの一意の ID をインデックスにマップします。|  
|[CListCtrl::MapIndexToID](#mapindextoid)|現在のリスト ビュー コントロール内の項目のインデックスを一意の ID にマップします。|  
|[CListCtrl::MoveGroup](#movegroup)|指定されたグループに移動します。|  
|[CListCtrl::MoveItemToGroup](#moveitemtogroup)|リスト ビュー コントロールの 0 から始まるインデックスを指定された、指定されたグループに移動します。|  
|[CListCtrl::RedrawItems](#redrawitems)|項目の範囲を再描画するリスト ビュー コントロールを強制します。|  
|[CListCtrl::RemoveAllGroups](#removeallgroups)|リスト ビュー コントロールからすべてのグループを削除します。|  
|[CListCtrl::RemoveGroup](#removegroup)|リスト ビュー コントロールから、指定されたグループを削除します。|  
|[CListCtrl::Scroll](#scroll)|リスト ビュー コントロールの内容をスクロールします。|  
|[CListCtrl::SetBkColor](#setbkcolor)|リスト ビュー コントロールの背景色を設定します。|  
|[CListCtrl::SetBkImage](#setbkimage)|リスト ビュー コントロールの現在の背景イメージを設定します。|  
|[CListCtrl::SetCallbackMask](#setcallbackmask)|リスト ビュー コントロールのコールバック マスクを設定します。|  
|[CListCtrl::SetCheck](#setcheck)|現在の表示の項目に関連付けられている状態の画像の状態を設定します。|  
|[CListCtrl::SetColumn](#setcolumn)|リスト ビューの列の属性を設定します。|  
|[CListCtrl::SetColumnOrderArray](#setcolumnorderarray)|リスト ビュー コントロールの列順序 (左右から) を設定します。|  
|[CListCtrl::SetColumnWidth](#setcolumnwidth)|レポート ビューまたはリスト ビュー内の列の幅を変更します。|  
|[かざして](#setextendedstyle)|リスト ビュー コントロールの現在の拡張スタイルを設定します。|  
|[CListCtrl::SetGroupInfo](#setgroupinfo)|リスト ビュー コントロールの指定したグループの情報を設定します。|  
|[CListCtrl::SetGroupMetrics](#setgroupmetrics)|リスト ビュー コントロールのグループのメトリックを設定します。|  
|[CListCtrl::SetHotCursor](#sethotcursor)|リスト ビュー コントロールのホット トラッキングが有効になっているときに使用するカーソルを設定します。|  
|[CListCtrl::SetHotItem](#sethotitem)|リスト ビュー コントロールの現在のホット項目を設定します。|  
|[CListCtrl::SetHoverTime](#sethovertime)|リスト ビュー コントロールの現在のホバー時の時刻を設定します。|  
|[CListCtrl::SetIconSpacing](#seticonspacing)|リスト ビュー コントロール内のアイコンの間隔を設定します。|  
|[CListCtrl::SetImageList](#setimagelist)|リスト ビュー コントロールにイメージ リストを割り当てます。|  
|[CListCtrl::SetInfoTip](#setinfotip)|ツールヒントのテキストを設定します。|  
|[CListCtrl::SetInsertMark](#setinsertmark)|定義済みの位置にカーソルを設定します。|  
|[CListCtrl::SetInsertMarkColor](#setinsertmarkcolor)|挿入ポイントの色を設定します。|  
|[CListCtrl::SetItem](#setitem)|リスト ビューの一部またはすべてを項目の属性を設定します。|  
|[CListCtrl::SetItemCount](#setitemcount)|多数のアイテムを追加するには、リスト ビュー コントロールを準備します。|  
|[CListCtrl::SetItemCountEx](#setitemcountex)|仮想リスト ビュー コントロールの項目数を設定します。|  
|[CListCtrl::SetItemData](#setitemdata)|項目のアプリケーション固有の値を設定します。|  
|[CListCtrl::SetItemIndexState](#setitemindexstate)|現在のリスト ビュー コントロールの項目の状態を設定します。|  
|[CListCtrl::SetItemPosition](#setitemposition)|リスト ビュー コントロール内の指定位置に項目を移動します。|  
|[CListCtrl::SetItemState](#setitemstate)|リスト ビュー コントロール内の項目の状態を変更します。|  
|[CListCtrl::SetItemText](#setitemtext)|リスト ビューの項目またはサブ項目のテキストを変更します。|  
|[CListCtrl::SetOutlineColor](#setoutlinecolor)|リスト ビュー コントロールの境界線の色を設定します。|  
|[CListCtrl::SetSelectedColumn](#setselectedcolumn)|リスト ビュー コントロールの選択した列を設定します。|  
|[CListCtrl::SetSelectionMark](#setselectionmark)|リスト ビュー コントロールの選択のマークを設定します。|  
|[CListCtrl::SetTextBkColor](#settextbkcolor)|リスト ビュー コントロールでテキストの背景色を設定します。|  
|[CListCtrl::SetTextColor](#settextcolor)|リスト ビュー コントロールのテキストの色を設定します。|  
|[CListCtrl::SetTileInfo](#settileinfo)|リスト ビュー コントロールのタイルの情報を設定します。|  
|[CListCtrl::SetTileViewInfo](#settileviewinfo)|タイル ビューでは、リスト ビュー コントロールを使用する情報を設定します。|  
|[CListCtrl::SetToolTips](#settooltips)|リスト ビュー コントロールがツールヒントの表示に使用するツール ヒント コントロールを設定します。|  
|[CListCtrl::SetView](#setview)|リスト ビュー コントロールのビューを設定します。|  
|[CListCtrl::SetWorkAreas](#setworkareas)|リスト ビュー コントロールにアイコンを表示する範囲を設定します。|  
|[CListCtrl::SortGroups](#sortgroups)|一覧のグループの並べ替えは、ユーザー定義関数でのコントロールを表示します。|  
|[CListCtrl::SortItems](#sortitems)|アプリケーション定義の比較関数を使用してリスト ビュー項目を並べ替えます。|  
|[CListCtrl::SortItemsEx](#sortitemsex)|アプリケーション定義の比較関数を使用してリスト ビュー項目を並べ替えます。|  
|[CListCtrl::SubItemHitTest](#subitemhittest)|指定された位置に存在する場合は、どのリスト ビューの項目を決定します。|  
|[CListCtrl::Update](#update)|コントロールが、指定した項目を描画するように強制します。|  
  
## <a name="remarks"></a>コメント  
 に加えて、アイコンとラベルの各項目がアイコンとラベルの右側の列に表示される情報を持つことができます。 このコントロール (したがって、`CListCtrl`クラス) は、Windows 95/98 および Windows NT 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 概要を次に示します、`CListCtrl`クラスです。 詳細な概念的な詳細については、次を参照してください。[使い方](../../mfc/using-clistctrl.md)と[コントロール](../../mfc/controls-mfc.md)です。  
  
## <a name="views"></a>ビュー  
 リスト ビュー コントロールが「ビュー」と呼ばれる 4 つの異なる方法でその内容を表示できます。  
  
-   アイコンの表示  
  
     各項目は、フル サイズのアイコン (32 x 32 ピクセル単位) の下にあるラベルとして表示されます。 ユーザーは、リスト ビュー ウィンドウで任意の場所に項目をドラッグできます。  
  
-   小さいアイコンの表示  
  
     各項目は、その右側にラベルを持つ小さなアイコン (16 x 16 ピクセル単位) として表示されます。 ユーザーは、リスト ビュー ウィンドウで任意の場所に項目をドラッグできます。  
  
-   リスト ビュー  
  
     各項目は、ラベルの右側に小さなアイコンとして表示されます。 項目は列に配置され、リスト ビュー ウィンドウで任意の場所にドラッグすることはできません。  
  
-   レポートの表示  
  
     各項目は、右側の列に追加の情報を含む独自の行に表示されます。 小さいアイコンとラベルを左端の列が含まれています、2 列目以降には、アプリケーションで指定されたサブ項目が含まれています。 埋め込みヘッダー コントロール (クラス[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)) これらの列を実装します。 ヘッダー コントロールおよびレポート ビューの列の詳細については、次を参照してください。[使い方: 列の追加 (レポート ビュー) のコントロールに](../../mfc/adding-columns-to-the-control-report-view.md)です。  
  
 関連項目:  
  
-   サポート技術情報の記事 Q250614: HOWTO: レポート ビューで CListCtrl の項目を並べ替える  
  
-   サポート技術情報の記事 Q200054: PRB: OnTimer() がないと呼ばれる繰り返しリスト コントロールの  
  
 コントロールの現在のリスト ビューのスタイルでは、現在のビューを決定します。 これらのスタイルとその使用方法の詳細については、次を参照してください。[使い方: リスト コントロール スタイルの変更](../../mfc/changing-list-control-styles.md)です。  
  
## <a name="extended-styles"></a>拡張スタイル  
 クラスの標準リスト スタイルに加え、`CListCtrl`豊富な機能を提供する、拡張スタイルの大規模なセットをサポートしています。 この機能のいくつかの例は次のとおりです。  
  
-   ホバー時の選択  
  
     有効にすると、カーソルが一定の時間の項目の上中に、項目の自動選択を許可します。  
  
-   仮想一覧の表示  
  
     有効な場合は、までをサポートするコントロール`DWORD`項目。 アプリケーションのアイテム データの管理のオーバーヘッドを配置することで可能です。 項目の選択とフォーカス情報を除くすべての項目については、アプリケーションで管理する必要があります。 詳細については、次を参照してください。[使い方: 仮想リスト コントロール](../../mfc/virtual-list-controls.md)です。  
  
-   クリック 1 回と 2 つのアクティブ化  
  
     有効な場合、(項目のテキストの自動強調表示) のホット トラッキングと強調表示されたアイテムのクリック 1 つまたは 2 つのアクティブ化を許可します。  
  
-   ドラッグ アンド ドロップ列の順序  
  
     有効にする場合は、ドラッグ アンド ドロップ リスト ビュー コントロール内の列の並べ替えを実行できます。 レポート ビューでのみ使用できます。  
  
 これらを新しい使用の詳細については、スタイルを拡張を参照してください[使い方: リスト コントロール スタイルの変更](../../mfc/changing-list-control-styles.md)です。  
  
## <a name="items-and-subitems"></a>アイテムとサブアイテム  
 リスト ビュー コントロール内の各項目は、(はイメージ リストのアイコン、ラベル、現在の状態、およびアプリケーション定義の値 (「項目のデータ」と呼ばれる) で構成されます。 1 つまたは複数のサブ項目は、各項目に関連付けられているできます。 「サブアイテム」は、レポート ビューでは、アイテムのアイコンとラベルの右側の列に表示可能な文字列です。 同じ数のサブ項目のリスト ビュー コントロール内のすべての項目が必要です。  
  
 クラス**CListCtrl**挿入、削除、検索、およびこれらの項目の変更のいくつかの機能を提供します。 詳細については、次を参照してください[CListCtrl::GetItem](#getitem)、 [CListCtrl::InsertItem](#insertitem)、および[CListCtrl::FindItem](#finditem)、 [コントロールへの項目の追加](../adding-items-to-the-control.md)。、および[スクロール、整列、並べ替え、およびリスト コントロール内の検索](../scrolling-arranging-sorting-and-finding-in-list-controls.md)です。  
  
 既定では、リスト ビュー コントロールが項目のアイコン、およびテキスト属性を格納します。 ただし、これらの項目の種類だけでなくクラス`CListCtrl`「コールバック項目」をサポートしています 「コールバック項目」は、対象のリスト ビュー項目アプリケーション — コントロールではなく、テキスト、アイコン、またはその両方を格納します。 コールバック マスクを使用して、アプリケーションによってどの項目の属性 (テキストまたはアイコン) を提供するを指定します。 アプリケーションでは、コールバック項目を使用する場合、要求時にテキストまたはアイコンの属性を提供できる必要があります。 コールバック項目は、この情報の一部を保持しているアプリケーション場合に便利です。 詳細については、次を参照してください。[使い方: コールバック項目とコールバック マスク](../callback-items-and-the-callback-mask.md)です。  
  
## <a name="image-lists"></a>イメージ リスト  
 アイコン、ヘッダー項目のイメージ、およびアプリケーションのリスト ビュー項目がいくつかのイメージ リストに含まれているため状態を定義 (クラスで実装された[CImageList](cimagelist-class.md)) を作成し、リスト ビュー コントロールに割り当てます。 各リスト ビュー コントロールには、最大で 4 つの異なる種類のイメージ リストを持つことができます。  
  
-   大きいアイコン  
  
     フル サイズのアイコンのアイコン表示で使用されます。  
  
-   小さいアイコン  
  
     アイコン表示で使用されるアイコンの縮小版の小さいアイコン、リスト、およびレポートのビューに使用します。  
  
-   アプリケーション定義の状態  
  
     アプリケーション定義の状態を示すために、アイテムのアイコンの横に表示される状態イメージが含まれています。  
  
-   ヘッダー項目  
  
     各ヘッダー コントロールの項目に表示される小さいイメージのレポート ビューで使用されます。  
  
 既定では、リスト ビュー コントロールが破棄されるときに、それに割り当てられているイメージ リストを破棄します。ただし、開発者は、アプリケーションによって決定されるを使用できなくする場合に各イメージ リストを破棄すると、この動作をカスタマイズできます。 詳細については、次を参照してください。[使い方: リスト項目とイメージ リスト](../list-items-and-image-lists.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CListCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="approximateviewrect"></a>  CListCtrl::ApproximateViewRect  
 幅とリスト ビュー コントロールの項目を表示するために必要な高さを決定します。  
  
```  
CSize ApproximateViewRect(
    CSize sz = CSize(-1,  
 -1),  
    int iCount = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `sz`  
 ピクセル単位で表したコントロールの寸法。 ディメンションが指定されていない場合、フレームワークは、コントロールの現在の幅または高さの値を使用します。  
  
 `iCount`  
 コントロールに表示される項目の数。 このパラメーターが-1 の場合は、フレームワークを使用して項目の合計数現在コントロールでします。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`おおよその幅と高さ (ピクセル単位)、項目を表示するために必要なを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_ApproximateViewRect](http://msdn.microsoft.com/library/windows/desktop/bb761231)Windows SDK で説明されている。  
  
##  <a name="arrange"></a>  CListCtrl::Arrange  
 アイコン表示で項目を再配置グリッド上に配置します。  
  
```  
BOOL Arrange(UINT nCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCode`  
 アイテムの配置スタイルを指定します。 次の値のいずれかを指定できます。  
  
- `LVA_ALIGNLEFT` ウィンドウの左の端にあるアイテムを整列します。  
  
- `LVA_ALIGNTOP` ウィンドウの上端に沿ってアイテムを整列します。  
  
- `LVA_DEFAULT` リスト ビューの現在の配置のスタイル (既定値) に基づいてアイテムを整列します。  
  
- `LVA_SNAPTOGRID` すべてのアイコンを最も近いグリッド位置にスナップされます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `nCode`配置スタイルを指定します。  
  
### <a name="example"></a>例    
```cpp  
    // Align all of the list view control items along the top
    // of the window (the list view control must be in icon or
    // small icon mode).
    m_myListCtrl.Arrange(LVA_ALIGNTOP);
```

  
##  <a name="canceleditlabel"></a>  CListCtrl::CancelEditLabel  
 項目のテキストの編集操作をキャンセルします。  
  
```  
void CancelEditLabel();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_CANCELEDITLABEL](http://msdn.microsoft.com/library/windows/desktop/bb774886)メッセージ、Windows SDK で説明します。  
  
##  <a name="clistctrl"></a>  CListCtrl::CListCtrl  
 `CListCtrl` オブジェクトを構築します。  
  
```  
CListCtrl();
```  
  
##  <a name="create"></a>  CListCtrl::Create  
 リスト コントロールを作成し、それにアタッチ、`CListCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 リスト コントロールのスタイルを指定します。 リスト コントロール スタイルの任意の組み合わせをコントロールに適用されます。 参照してください[リスト ビュー ウィンドウ スタイル](http://msdn.microsoft.com/library/windows/desktop/bb774739)これらのスタイルの完全な一覧については Windows SDK に含まれています。 拡張を使用してコントロールに固有のスタイル セット[拡張](#setextendedstyle)です。  
  
 `rect`  
 リスト コントロールのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
 `pParentWnd`  
 通常、リスト コントロールの親ウィンドウを指定します、`CDialog`です。 なければなりません**NULL**です。  
  
 `nID`  
 リスト コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CListCtrl` 2 つの手順でします。 最初に、コンス トラクターを呼び出すし、呼び出す**作成**、リスト ビュー コントロールを作成しにアタッチする、`CListCtrl`オブジェクト。  
  
 リスト コントロール オブジェクトに拡張ウィンドウ スタイルを適用するには、呼び出す[CreateEx](#createex)の代わりに**作成**です。  
  
### <a name="example"></a>例  

```cpp  
    m_myListCtrl.Create(
        WS_CHILD|WS_VISIBLE|WS_BORDER|LVS_REPORT|LVS_EDITLABELS,
        CRect(10,10,400,200), pParentWnd, IDD_MYLISTCTRL);   
```

  
##  <a name="createex"></a>  CListCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成しに関連付けます、`CListCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 `dwStyle`  
 リスト コントロールのスタイルを指定します。 リスト コントロール スタイルの任意の組み合わせをコントロールに適用されます。 これらのスタイルの一覧については、次を参照してください。[リスト ビュー ウィンドウ スタイル](http://msdn.microsoft.com/library/windows/desktop/bb774739)Windows SDK に含まれています。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体`pParentWnd`です。  
  
 `pParentWnd`  
 コントロールの親であるウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
 `CreateEx` 指定された拡張ウィンドウ スタイルでコントロールが作成され`dwExStyle`です。 コントロール固有の拡張スタイルを設定するには、呼び出す[拡張](#setextendedstyle)です。 たとえば、使用して`CreateEx`としてこのようなスタイルを設定する**WS_EX_CONTEXTHELP**が使用して`SetExtendedStyle`としてこのようなスタイルを設定する**LVS_EX_FULLROWSELECT**です。 詳細については、トピックで説明されているスタイルを参照してください。[リスト ビューのスタイルの拡張](http://msdn.microsoft.com/library/windows/desktop/bb774732)Windows SDK に含まれています。  
  
##  <a name="createdragimage"></a>  CListCtrl::CreateDragImage  
 指定した項目のドラッグ イメージ リストを作成`nItem`です。  
  
```  
CImageList* CreateDragImage(
    int nItem,  
    LPPOINT lpPoint);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 作成するのには、ドラッグ イメージ リストを持つ項目のインデックス。  
  
 `lpPoint`  
 アドレス、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)画像の左上隅の最初の場所を受信する座標でします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、ドラッグ イメージのリストへのポインターそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 `CImageList`オブジェクトが保存され、作業完了後に削除する必要があります。 例えば:  
  

```cpp  
        CImageList* pImageList = m_myListCtrl.CreateDragImage(nItem, &point);

        // do something

        delete pImageList;
```

  
##  <a name="deleteallitems"></a>  CListCtrl::DeleteAllItems  
 リスト ビュー コントロールからすべての項目を削除します。  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  

```cpp  
    // Delete all of the items from the list view control.
    m_myListCtrl.DeleteAllItems();
    ASSERT(m_myListCtrl.GetItemCount() == 0);
```

  
##  <a name="deletecolumn"></a>  CListCtrl::DeleteColumn  
 リスト ビュー コントロールから列を削除します。  
  
```  
BOOL DeleteColumn(int nCol);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCol`  
 削除する列のインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  

```cpp  
        int nColumnCount = m_myListCtrl.GetHeaderCtrl()->GetItemCount();

        // Delete all of the columns.
        for (int i=0; i < nColumnCount; i++)
        {
            m_myListCtrl.DeleteColumn(0);
        }
```

  
##  <a name="deleteitem"></a>  CListCtrl::DeleteItem  
 リスト ビュー コントロールから項目を削除します。  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 削除する項目のインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
```cpp  
        int nCount = m_myListCtrl.GetItemCount();

        // Delete all of the items from the list view control.
        for (int i=0; i < nCount; i++)
        {
            m_myListCtrl.DeleteItem(0);
        }
```

  
##  <a name="drawitem"></a>  CListCtrl::DrawItem  
 オーナー描画リスト ビュー コントロールの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 Long ポインター、`DRAWITEMSTRUCT`のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**のメンバー、 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802)構造体を実行するのには、描画の動作を定義します。  
  
 既定では、このメンバー関数では何も行いません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CListCtrl`オブジェクト。  
  
 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`関数はこのメンバーの前に終了します。  
  
##  <a name="editlabel"></a>  CListCtrl::EditLabel  
 インプレースでのアイテムのテキストの編集を開始します。  
  
```  
CEdit* EditLabel(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 編集するのには、リスト ビューの項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合へのポインター、`CEdit`項目テキストの編集に使用されます。 それ以外の場合は、オブジェクト**NULL**です。  
  
### <a name="remarks"></a>コメント  
 リスト ビュー コントロールを持つ、`LVS_EDITLABELS`ウィンドウ スタイルの場所で項目のラベルを編集するユーザーを有効にします。 ユーザーは、フォーカスがある項目のラベルをクリックして編集を開始します。  
  
 インプレースでは、指定されたリスト ビュー項目のテキストの編集を開始するのにには、この関数を使用します。  
  
### <a name="example"></a>例  
```cpp  
        // Make sure the focus is set to the list view control.
        m_myListCtrl.SetFocus();

        // Show the edit control on the label of the first
        // item in the list view control.
        CEdit* pmyEdit = m_myListCtrl.EditLabel(1);
        ASSERT(pmyEdit != NULL);
```

  
##  <a name="enablegroupview"></a>  CListCtrl::EnableGroupView  
 有効またはリスト ビュー コントロール内の項目をグループとして表示するかどうかを無効にします。  
  
```  
LRESULT EnableGroupView(BOOL fEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `fEnable`  
 表示項目をグループに listview コントロールを有効にするかどうかを示します。 **TRUE**をグループ化を有効にするには**FALSE**を無効にします。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
- **0**をリスト ビューを表示できる項目をグループが既に有効になっているか、無効になっているとします。  
  
- **1**コントロールの状態が正常に変更します。  
  
- **-1**操作に失敗しました。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_ENABLEGROUPVIEW](http://msdn.microsoft.com/library/windows/desktop/bb774900)メッセージ、Windows SDK で説明します。  
  
##  <a name="ensurevisible"></a>  CListCtrl::EnsureVisible  
 により、リスト ビューの項目には、少なくとも部分的に表示されなくなります。  
  
```  
BOOL EnsureVisible(
    int nItem,  
    BOOL bPartialOK);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 表示するのには、リスト ビューの項目のインデックス。  
  
 `bPartialOK`  
 部分的な可視性が許容されるかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、リスト ビュー コントロールがスクロールされます。 場合、`bPartialOK`パラメーターがゼロ以外、スクロールは行われません、アイテムが部分的に表示されるかどうか。  
  
### <a name="example"></a>例  
```cpp  
        // Ensure that the last item is visible.
        int nCount = m_myListCtrl.GetItemCount();
        if (nCount > 0)
            m_myListCtrl.EnsureVisible(nCount-1, FALSE);
```

  
##  <a name="finditem"></a>  CListCtrl::FindItem  
 指定した特性を持つリスト ビューの項目を検索します。  
  
```  
int FindItem(
    LVFINDINFO* pFindInfo,  
    int nStart = -1) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pFindInfo`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774745)を検索する項目に関する情報を含む構造体。  
  
 `nStart`  
 を使用して検索を開始するアイテムを最初から開始する場合は-1 のインデックス。 位置にある項目`nStart`場合は、検索から除外`nStart`が-1 に等しくないです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合、項目またはそれ以外の場合に-1 のインデックス。  
  
### <a name="remarks"></a>コメント  
 `pFindInfo`パラメーターが指し示す、**保持**構造体は、リスト ビューの項目の検索に使用される情報が含まれています。  
  
### <a name="example"></a>例  

```cpp  
        LVFINDINFO info;
        int nIndex;

        info.flags = LVFI_PARTIAL|LVFI_STRING;
        info.psz = _T("item");

        // Delete all of the items that begin with the string.
        while ((nIndex = m_myListCtrl.FindItem(&info)) != -1)
        {
            m_myListCtrl.DeleteItem(nIndex);
        }
```

  
##  <a name="getbkcolor"></a>  CListCtrl::GetBkColor  
 リスト ビュー コントロールの背景色を取得します。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色を指定するために使用する 32 ビット値です。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::SetBkColor](#setbkcolor)です。  
  
##  <a name="getbkimage"></a>  CListCtrl::GetBkImage  
 リスト ビュー コントロールの現在の背景イメージを取得します。  
  
```  
BOOL GetBkImage(LVBKIMAGE* plvbkImage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `plvbkImage`  
 ポインター、**格納されて**リスト ビューの現在の背景イメージを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外を返します。 または 0 それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 マクロの動作を実装[ListView_GetBkImage](http://msdn.microsoft.com/library/windows/desktop/bb761246)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

```cpp  
        LVBKIMAGE bki;

        // If no background image is set for the list view control use
        // the Microsoft homepage image as the background image.
        if (m_myListCtrl.GetBkImage(&bki) && (bki.ulFlags == LVBKIF_SOURCE_NONE))
        {
            m_myListCtrl.SetBkImage(
                _T("http://www.microsoft.com/library/images/gifs/homepage/microsoft.gif"),
                TRUE);
        }
```

  
##  <a name="getcallbackmask"></a>  CListCtrl::GetCallbackMask  
 リスト ビュー コントロールのコールバック マスクを取得します。  
  
```  
UINT GetCallbackMask() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロールのコールバック マスクです。  
  
### <a name="remarks"></a>コメント  
 「コールバック項目」は、対象のリスト ビュー項目アプリケーション — コントロールではなく、テキスト、アイコン、またはその両方を格納します。 リスト ビュー コントロールは、これらの属性を格納するため、既にアプリケーションには、この情報の一部が保持している場合は、コールバック項目を使用することがあります。 コールバック マスクは、どの項目の状態ビットは、アプリケーションで保持されますを指定し、特定の項目ではなく、コントロール全体に適用されます。 コールバック マスクは、既定では、コントロールがすべての項目の状態を追跡することを意味する 0 です。 アプリケーションでは、コールバックのアイテムを使用または 0 以外のコールバック マスクを指定します、オンデマンドでリスト ビュー項目属性を提供できる必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::SetCallbackMask](#setcallbackmask)です。  
  
##  <a name="getcheck"></a>  CListCtrl::GetCheck  
 項目に関連付けられている状態のイメージの現在の表示状態を取得します。  
  
```  
BOOL GetCheck(int nItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 リスト コントロール項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 項目が選択されている場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetCheckState](http://msdn.microsoft.com/library/windows/desktop/bb761250)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::SetCheck](#setcheck)です。  
  
##  <a name="getcolumn"></a>  CListCtrl::GetColumn  
 リスト ビュー コントロールの列の属性を取得します。  
  
```  
BOOL GetColumn(
    int nCol,  
    LVCOLUMN* pColumn) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nCol`  
 属性を取得する列のインデックス。  
  
 `pColumn`  
 アドレス、 [LVCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743)構造体を取得する情報を指定し、列に関する情報を受け取る。 **マスク**のどの列属性を取得するメンバーを指定します。 場合、**マスク**メンバーを指定します、`LVCF_TEXT`値、 **pszText**メンバーは、項目のテキストを受け取るバッファーのアドレスを含める必要があります、 **cchTextMax**メンバーは、バッファーのサイズを指定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **LVCOLUMN**構造体には、レポート ビューの列に関する情報が含まれています。  
  
### <a name="example"></a>例  

```cpp  
        LVCOLUMN col;

        col.mask = LVCF_WIDTH;

        // Double the column width of the first column.
        if (m_myListCtrl.GetColumn(0, &col))
        {
            col.cx *= 2;
            m_myListCtrl.SetColumn(0, &col);
        }
```

  
##  <a name="getcolumnorderarray"></a>  CListCtrl::GetColumnOrderArray  
 リスト ビュー コントロールの列順序 (左右から) を取得します。  
  
```  
BOOL GetColumnOrderArray(
    LPINT piArray,  
    int iCount = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `piArray`  
 リスト ビュー コントロール内の列のインデックス値を格納するバッファーへのポインター。 バッファーは、リスト ビュー コントロール内の列の合計数を格納するのに十分な大きさである必要があります。  
  
 `iCount`  
 リスト ビュー コントロール内の列の数。 このパラメーターが-1 の場合は、列の数は、フレームワークによって自動的に取得されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetColumnOrderArray](http://msdn.microsoft.com/library/windows/desktop/bb761254)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

```cpp  
        // Reverse the order of the columns in the list view control
        // (i.e. make the first column the last, the last column
        // the first, and so on...).
        CHeaderCtrl* pHeaderCtrl = m_myListCtrl.GetHeaderCtrl();

        if (pHeaderCtrl != NULL)
        {
            int  nColumnCount = pHeaderCtrl->GetItemCount();
            LPINT pnOrder = (LPINT) malloc(nColumnCount*sizeof(int));
            ASSERT(pnOrder != NULL);
m_myListCtrl.GetColumnOrderArray(pnOrder, nColumnCount);

            int i, j, nTemp;
            for (i = 0, j = nColumnCount-1; i < j; i++, j--)
            {
                nTemp = pnOrder[i];
                pnOrder[i] = pnOrder[j];
                pnOrder[j] = nTemp;
            }

            m_myListCtrl.SetColumnOrderArray(nColumnCount, pnOrder);
            free(pnOrder);
        }
```

  
##  <a name="getcolumnwidth"></a>  CListCtrl::GetColumnWidth  
 レポート ビューまたはリスト ビュー内の列の幅を取得します。  
  
```  
int GetColumnWidth(int nCol) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nCol`  
 幅を取得する列のインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 幅 (ピクセル単位) で指定された列の`nCol`します。  
  
### <a name="example"></a>例  

```cpp  
        // Increase the column width of the second column by 20.
        int nWidth = m_myListCtrl.GetColumnWidth(1);
        m_myListCtrl.SetColumnWidth(1, 20 + nWidth);
```

  
##  <a name="getcountperpage"></a>  CListCtrl::GetCountPerPage  
 リスト ビューまたはレポート ビューでリスト ビュー コントロールの表示領域の垂直方向に収まる項目数を計算します。  
  
```  
int GetCountPerPage() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビューまたはレポート ビューでリスト ビュー コントロールの表示領域の垂直方向に収まる項目数。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetTopIndex](#gettopindex)です。  
  
##  <a name="geteditcontrol"></a>  CListCtrl::GetEditControl  
 リスト ビュー項目のテキストを編集するために使用するエディット コントロールのハンドルを取得します。  
  
```  
CEdit* GetEditControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合へのポインター、 [CEdit](cedit-class.md)項目テキストの編集に使用されます。 それ以外の場合は、オブジェクト**NULL**です。  
  
### <a name="example"></a>例  

```cpp  
        // The string replacing the text in the edit control.
        LPCTSTR lpszmyString = _T("custom label!");

        // If possible, replace the text in the label edit control.
        CEdit* pEdit = m_myListCtrl.GetEditControl();

        if (pEdit != NULL)
        {
            pEdit->SetWindowText(lpszmyString);
        }
```

  
##  <a name="getemptytext"></a>  CListCtrl::GetEmptyText  
 現在のリスト ビュー コントロールが空の場合に表示する文字列を取得します。  
  
```  
CString GetEmptyText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)コントロールが空の場合に表示するテキストを格納しています。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_GETEMPTYTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774921) Windows SDK で説明するメッセージ。  
  
##  <a name="getextendedstyle"></a>  CListCtrl::GetExtendedStyle  
 リスト ビュー コントロールの現在の拡張スタイルを取得します。  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>戻り値  
 一覧で使用されている拡張スタイルの組み合わせでは、コントロールを表示します。 わかりやすいのこれらの拡張スタイルの一覧を表示するには、次を参照してください。、[拡張のリスト ビュー スタイル](http://msdn.microsoft.com/library/windows/desktop/bb774732)Windows SDK のトピックです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetExtendedListViewStyle](http://msdn.microsoft.com/library/windows/desktop/bb761264)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[かざして](#setextendedstyle)です。  
  
##  <a name="getfirstselecteditemposition"></a>  CListCtrl::GetFirstSelectedItemPosition  
 最初に選択した項目のリスト ビュー コントロール内の位置を取得します。  
  
```  
POSITION GetFirstSelectedItemPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得に使用できる値**NULL**項目が選択されていない場合。  
  
### <a name="example"></a>例  
 次のコード サンプルは、この関数の使用法を示しています。  
  

```cpp  
        POSITION pos = m_myListCtrl.GetFirstSelectedItemPosition();
        if (pos == NULL)
        {
            TRACE(_T("No items were selected!\n"));
        }
        else
        {
            while (pos)
            {
                int nItem = m_myListCtrl.GetNextSelectedItem(pos);
                TRACE(_T("Item %d was selected!\n"), nItem);
                // you could do your own processing on nItem here
            }
        }
```

  
##  <a name="getfocusedgroup"></a>  CListCtrl::GetFocusedGroup  
 現在のリスト ビュー コントロールにキーボード フォーカスのあるグループを取得します。  
  
```  
int GetFocusedGroup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 状態があるグループのインデックス`LVGS_FOCUSED`; このようなグループがある場合は、それ以外の場合、-1。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_GETFOCUSEDGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774925) Windows SDK で説明するメッセージ。 詳細については、次を参照してください。、`LVGS_FOCUSED`の値、`state`のメンバー、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)構造体。  
  
##  <a name="getgroupcount"></a>  CListCtrl::GetGroupCount  
 現在のリスト ビュー コントロール内のグループの数を取得します。  
  
```  
int GetGroupCount()const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロール内のグループの数。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_GETGROUPCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774931) Windows SDK に説明されているメッセージ: です。  
  
##  <a name="getgroupinfo"></a>  CListCtrl::GetGroupInfo  
 リスト ビュー コントロールの指定されたグループの情報を取得します。  
  
```  
int GetGroupInfo(
    int iGroupId,  
    PLVGROUP pgrp) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iGroupId`  
 その情報を取得するグループの識別子。  
  
 `pgrp`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)指定されたグループに関する情報を格納します。  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、グループの成功した場合、または-1 の ID を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETGROUPINFO](http://msdn.microsoft.com/library/windows/desktop/bb774932)メッセージ、Windows SDK で説明します。  
  
##  <a name="getgroupinfobyindex"></a>  CListCtrl::GetGroupInfoByIndex  
 現在のリスト ビュー コントロール内の指定されたグループに関する情報を取得します。  
  
```  
BOOL GetGroupInfoByIndex(
    int iIndex,   
    PLVGROUP pGroup) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iIndex`|グループの 0 から始まるインデックス。|  
|[出力] `pGroup`|ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)構造体で指定されたグループに関する情報を受け取る、`iIndex`パラメーター。<br /><br /> メンバーを初期化するため、呼び出し元が、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)構造体。 設定、 `cbSize` 、構造体のサイズおよびのフラグにはメンバー、`mask`メンバーを取得する情報を指定します。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_GETGROUPINFOBYINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774933) Windows SDK に説明されているメッセージ: です。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_listCtrl`、つまり現在のリスト ビュー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  

```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>例  
 次のコード例を示しています、`GetGroupInfoByIndex`メソッドです。 このコードの前のセクションでは、リスト ビュー コントロールを作成した例は、レポート ビューの"ClientID"および"Grade"をという 2 つの列を表示します。 次のコード例は、このようなグループが存在する場合に、インデックスが 0、グループに関する情報を取得します。    
```cpp  
    // GetGroupInfoByIndex
    const int GROUP_HEADER_BUFFER_SIZE = 40;

// Initialize the structure 
    LVGROUP gInfo = {0};
    gInfo.cbSize = sizeof(LVGROUP);
    wchar_t wstrHeadGet[GROUP_HEADER_BUFFER_SIZE] = {0};
    gInfo.cchHeader = GROUP_HEADER_BUFFER_SIZE;
    gInfo.pszHeader = wstrHeadGet;
    gInfo.mask = (LVGF_ALIGN | LVGF_STATE | LVGF_HEADER | LVGF_GROUPID);
    gInfo.state = LVGS_NORMAL;
    gInfo.uAlign  = LVGA_HEADER_LEFT;

    BOOL bRet = m_listCtrl.GetGroupInfoByIndex( 0, &gInfo );
    if (bRet == TRUE) {
        CString strHeader = CString( gInfo.pszHeader );
        CString str;
        str.Format(_T("Header: '%s'"), strHeader);
        AfxMessageBox(str, MB_ICONINFORMATION);
    }
    else
    {
        AfxMessageBox(_T("No group information was retrieved."));
    }
```

  
##  <a name="getgroupmetrics"></a>  CListCtrl::GetGroupMetrics  
 グループのメトリックを取得します。  
  
```  
void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroupMetrics`  
 ポインター、 [LVGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb774752)グループ メトリック情報を格納します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb774934)メッセージ、Windows SDK で説明します。  
  
##  <a name="getgrouprect"></a>  CListCtrl::GetGroupRect  
 現在のリスト ビュー コントロール内の指定したグループの外接する四角形を取得します。  
  
```  
BOOL GetGroupRect(
    int iGroupId,   
    LPRECT lpRect,   
    int iCoords = LVGGR_GROUP) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iGroupId`|グループを指定します。|  
|[入力、出力] `lpRect`|ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。 このメソッドが成功するが構造体で指定されているグループの四角形の座標`iGroupId`です。|  
|[入力] `iCoords`|取得する四角形の座標を指定します。 これらの値のいずれかを使用します。<br /><br /> - `LVGGR_GROUP` -展開されたグループ全体の座標を (既定値)。<br />- `LVGGR_HEADER` (折りたたまれたグループ) のヘッダーのみの座標。<br />- `LVGGR_SUBSETLINK` 座標のサブセットのリンク (マークアップ サブセット) だけです。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 割り当てるための呼び出し元が、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体を指す、`pRect`パラメーター。  
  
 このメソッドは、送信、 [LVM_GETGROUPRECT](http://msdn.microsoft.com/library/windows/desktop/bb774935) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_listCtrl`、つまり現在のリスト ビュー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。    
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>例  
 次のコード例を示しています、`GetGroupRect`メソッドです。 このコード例の前のセクションでは、レポート ビューの"ClientID"および"Grade"をという 2 つの列を表示するリスト ビュー コントロールを作成しました。 次のコード例は、このようなグループが存在する場合、インデックスが 0、グループの周囲の 3D の四角形を描画します。    
  
```cpp  
    // GetGroupRect

    // Get the graphics rectangle that surrounds group 0.
    CRect rect;
    BOOL bRet = m_listCtrl.GetGroupRect( 0, &rect, LVGGR_GROUP); 
    // Draw a blue rectangle around group 0.
    if (bRet == TRUE) {
        m_listCtrl.GetDC()->Draw3dRect( &rect, RGB(0, 0, 255), RGB(0, 0, 255));
    }
    else {
        AfxMessageBox(_T("No group information was retrieved."), MB_ICONINFORMATION);
    }
```

  
##  <a name="getgroupstate"></a>  CListCtrl::GetGroupState  
 現在のリスト ビュー コントロール内の指定したグループの状態を取得します。  
  
```  
UINT GetGroupState(
    int iGroupId,   
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iGroupId`|グループの 0 から始まるインデックス。|  
|[入力] `dwMask`|指定したグループを取得する状態の値を指定するマスク。 詳細については、次を参照してください。、`mask`のメンバー、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)構造体。|  
  
### <a name="return-value"></a>戻り値  
 指定したグループまたはグループが見つからない場合は 0 の要求された状態です。  
  
### <a name="remarks"></a>コメント  
 戻り値のビットごとの AND 演算の結果は、`dwMask`パラメーターと値の`state`のメンバー、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)を現在のリスト ビュー コントロールを表す構造です。  
  
 このメソッドは、送信、 [LVM_GETGROUPSTATE](http://msdn.microsoft.com/library/windows/desktop/bb774936) Windows SDK で説明するメッセージ。 詳細については、次を参照してください。、 [ListView_GetGroupState](http://msdn.microsoft.com/library/windows/desktop/bb761288)マクロです。  
  
##  <a name="getheaderctrl"></a>  CListCtrl::GetHeaderCtrl  
 リスト ビュー コントロールのヘッダー コントロールを取得します。  
  
```  
CHeaderCtrl* GetHeaderCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロールによって使用される、ヘッダー コントロールへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetHeader](http://msdn.microsoft.com/library/windows/desktop/bb761290)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetColumnOrderArray](#getcolumnorderarray)です。  
  
##  <a name="gethotcursor"></a>  CListCtrl::GetHotCursor  
 リスト ビュー コントロールのホット トラッキングが有効になっているときに使用するカーソルを取得します。  
  
```  
HCURSOR GetHotCursor();
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロールで使用されている現在のカーソルのホット リソースへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetHotCursor](http://msdn.microsoft.com/library/windows/desktop/bb761292)Windows SDK で説明されている。 ホバー時の選択範囲が有効になっているときにだけ表示ホット カーソルには、カーソルが、リスト ビューの項目を置いたときに表示されます。 ホバー時の選択範囲が有効になって、 **LVS_EX_TRACKSELECT**拡張スタイル。  
  
### <a name="example"></a>例    
  
```cpp  
        // Set the hot cursor to be the system app starting cursor.
        HCURSOR hCursor = ::LoadCursor(NULL, IDC_APPSTARTING);
        m_myListCtrl.SetHotCursor(hCursor);
        ASSERT(m_myListCtrl.GetHotCursor() == hCursor);
```

  
##  <a name="gethotitem"></a>  CListCtrl::GetHotItem  
 カーソルの下に現在のリスト ビューの項目を取得します。  
  
```  
int GetHotItem();
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロールの現在のホット項目のインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetHotItem](http://msdn.microsoft.com/library/windows/desktop/bb761294)Windows SDK で説明されている。 ホット アイテムはホット トラッキング (とホバー選択) 場合は、現在選択されている項目が有効になっているように定義されます。  
  
 ホット トラッキングが有効な場合、ユーザーがリスト ビューの項目上に置いたときに、マウス ボタンを使用せず項目ラベルが自動的に強調表示します。  
  
### <a name="example"></a>例    
  
```cpp  
    // Set the hot item to the first item only if no other item is 
    // highlighted.
    if (m_myListCtrl.GetHotItem() == -1)
        m_myListCtrl.SetHotItem(0);
```

  
##  <a name="gethovertime"></a>  CListCtrl::GetHoverTime  
 リスト ビュー コントロールの現在のホバー時の時刻を取得します。  
  
```  
DWORD GetHoverTime() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択されている前に、アイテムの上、マウス カーソルを合わせて、ミリ秒単位で、遅延時間を返します。 戻り値が-1 の場合は、既定ホバー時の時間はホバー時です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetHoverTime](http://msdn.microsoft.com/library/windows/desktop/bb761296)Windows SDK で説明されている。  
  
### <a name="example"></a>例    
  
```cpp  
        // If the hover time is the default set to 1 sec.
        DWORD dwTime = m_myListCtrl.GetHoverTime();
        if (dwTime == -1)
            m_myListCtrl.SetHoverTime(1000);
```

  
##  <a name="getimagelist"></a>  CListCtrl::GetImageList  
 描画のリスト ビュー項目を使用するイメージ リストのハンドルを取得します。  
  
```  
CImageList* GetImageList(int nImageList) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nImageList`  
 取得するには、どのイメージ リストを指定する値。 これらの値のいずれかを指定できます。  
  
- `LVSIL_NORMAL` 大きいアイコンのイメージ リスト。  
  
- `LVSIL_SMALL` 小さいアイコンのイメージ リスト。  
  
- `LVSIL_STATE` 状態のイメージのイメージ リスト。  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー項目を描画するために使用するイメージ リストへのポインター。  
  
### <a name="example"></a>例    
  
```cpp  
        ASSERT(m_myListCtrl.GetImageList(LVSIL_NORMAL) == NULL);
m_myListCtrl.SetImageList(&m_lcImageList, LVSIL_NORMAL);
        ASSERT(m_myListCtrl.GetImageList(LVSIL_NORMAL) == &m_lcImageList);
```

  
##  <a name="getinsertmark"></a>  CListCtrl::GetInsertMark  
 挿入マークの現在の位置を取得します。  
  
```  
BOOL GetInsertMark(LPLVINSERTMARK lvim) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lvim`  
 ポインター、 [LVINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774758)挿入マークの情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、または**FALSE**それ以外の場合。 **FALSE**場合に返されるサイズで、`cbSize`のメンバー、 **LVINSERTMARK**構造体は、構造体の実際のサイズと一致しません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774945)メッセージ、Windows SDK で説明します。  
  
##  <a name="getinsertmarkcolor"></a>  CListCtrl::GetInsertMarkColor  
 挿入マークの現在の色を取得します。  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)挿入ポイントの色を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774947)メッセージ、Windows SDK で説明します。  
  
##  <a name="getinsertmarkrect"></a>  CListCtrl::GetInsertMarkRect  
 挿入ポイントの外接する四角形を取得します。  
  
```  
int GetInsertMarkRect(LPRECT pRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pRect`  
 ポインター、`RECT`挿入ポイントの外接する四角形の座標を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
- **0**挿入ポイントなし。  
  
- **1**挿入ポイントが見つかりませんでした。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETINSERTMARKRECT](http://msdn.microsoft.com/library/windows/desktop/bb774949)メッセージ、Windows SDK で説明します。  
  
##  <a name="getitem"></a>  CListCtrl::GetItem  
 リスト ビュー項目の属性の一部またはすべてを取得します。  
  
```  
BOOL GetItem(LVITEM* pItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760)項目の属性を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **LVITEM**構造体を指定またはリスト ビューの項目の属性を受信します。  
  
##  <a name="getitemcount"></a>  CListCtrl::GetItemCount  
 リスト ビュー コントロール内の項目数を取得します。  
  
```  
int GetItemCount() const; 
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロール内の項目の数。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::DeleteItem](#deleteitem)です。  
  
##  <a name="getitemdata"></a>  CListCtrl::GetItemData  
 指定した項目に関連付けられている 32 ビット アプリケーションに固有の値を取得`nItem`です。  
  
```  
DWORD_PTR GetItemData(int nItem) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 テーブルのデータを取得するリスト項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定した項目に関連付けられている 32 ビット アプリケーションに固有の値。  
  
### <a name="remarks"></a>コメント  
 この値は、 **lParam**のメンバー、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) Windows SDK」の説明に従って、構造体  
  
### <a name="example"></a>例  

```cpp  
    // If any item's data is equal to zero then reset it to -1.
    for (int i=0; i < m_myListCtrl.GetItemCount(); i++)
    {
        if (m_myListCtrl.GetItemData(i) == 0)
        {
            m_myListCtrl.SetItemData(i, (DWORD) -1);
        }
    }
```

  
##  <a name="getitemindexrect"></a>  CListCtrl::GetItemIndexRect  
 現在のリスト ビュー コントロール内のサブアイテムの全部または一部の外接する四角形を取得します。  
  
```  
BOOL GetItemIndexRect(
    PLVITEMINDEX pItemIndex,   
    int iColumn,   
    int rectType,   
    LPRECT pRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pItemIndex`|ポインター、[記述](http://msdn.microsoft.com/library/windows/desktop/bb774762)サブ項目の親項目の構造体。<br /><br /> 呼び出し元が割り当てと設定のメンバーを担当する、[記述](http://msdn.microsoft.com/library/windows/desktop/bb774762)構造体。 このパラメーターを指定できません`NULL`です。|  
|[入力] `iColumn`|コントロール内の列の 0 から始まるインデックス。|  
|[入力] `rectType`|外接する四角形を取得するリスト ビューのサブアイテムの部分です。 次のいずれかの値を指定します。<br /><br /> `LVIR_BOUNDS` -全体のサブ、アイコンとラベルを含む項目の外接する四角形を返します。<br /><br /> `LVIR_ICON` -アイコンまたは小さいアイコンのサブ項目の外接する四角形を返します。<br /><br /> `LVIR_LABEL` -サブ項目のテキストの外接する四角形を返します。|  
|[出力] `pRect`|ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)サブ項目の外接する四角形に関する情報を受け取る構造体。<br /><br /> 割り当てるための呼び出し元が、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。 このパラメーターを指定できません`NULL`です。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_GETITEMINDEXRECT](http://msdn.microsoft.com/library/windows/desktop/bb761046) Windows SDK で説明するメッセージ。 詳細については、次を参照してください。 [ListView_GetItemIndexRect マクロ](http://msdn.microsoft.com/library/windows/desktop/bb774959)です。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_listCtrl`、つまり現在のリスト ビュー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。    
  
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>例  
 次のコード例を示しています、`GetGroupRect`メソッドです。 このコードを入力する前に、リスト ビュー コントロールを作成した例は、レポート ビューの"ClientID"および"Grade"をという 2 つの列を表示します。 次のコード例では、両方の列に 2 つ目のサブアイテムの周りの 3D の四角形を描画します。    
  
```cpp  
    // GetItemIndexRect
    // Get the rectangle that bounds the second item in the first group.
    LVITEMINDEX lvItemIndex;
    lvItemIndex.iGroup = 0;
    lvItemIndex.iItem = 1;
    CRect rect;
    BOOL bRet = m_listCtrl.GetItemIndexRect(
        &lvItemIndex, 0, LVIR_BOUNDS, &rect);

    // Draw a red rectangle around the item.
    m_listCtrl.GetDC()->Draw3dRect( &rect, RGB(255, 0, 0), RGB(255, 0, 0) );
```

  
##  <a name="getitemposition"></a>  CListCtrl::GetItemPosition  
 リスト ビューの項目の位置を取得します。  
  
```  
BOOL GetItemPosition(
    int nItem,  
    LPPOINT lpPoint) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 位置を取得する項目のインデックス。  
  
 `lpPoint`  
 アドレス、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)アイテムの左上隅の位置を受け取る座標でします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例    
  
```cpp  
        POINT pt;

        // Move all items in the list control 100 pixels to the right.
        UINT i, nCount = m_myListCtrl.GetItemCount();

        for (i=0; i < nCount; i++)
        {
            m_myListCtrl.GetItemPosition(i, &pt);
            pt.x += 100;
            m_myListCtrl.SetItemPosition(i, pt);
        }   
```

  
##  <a name="getitemrect"></a>  CListCtrl::GetItemRect  
 現在のビュー内の項目のすべてまたは一部の外接する四角形を取得します。  
  
```  
BOOL GetItemRect(
    int nItem,  
    LPRECT lpRect,  
    UINT nCode) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 位置を取得する項目のインデックス。  
  
 `lpRect`  
 アドレス、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形を受け取る。  
  
 `nCode`  
 外接する四角形を取得する対象のリスト ビューの項目の部分です。 これらの値のいずれかを指定できます。  
  
- `LVIR_BOUNDS` アイコンとラベルを含む、アイテム全体の外接する四角形を返します。  
  
- `LVIR_ICON` アイコンまたは小さいアイコンに外接する四角形を返します。  
  
- `LVIR_LABEL` 項目のテキストの外接する四角形を返します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例    
  
```cpp  
// OnClick is the handler for the NM_CLICK notification
void CListCtrlDlg::OnClick(NMHDR* pNMHDR, LRESULT* pResult)
{
    UNREFERENCED_PARAMETER(pResult);
LPNMITEMACTIVATE pia = (LPNMITEMACTIVATE)pNMHDR;

    // Get the current mouse location and convert it to client
    // coordinates.
    CPoint pos( ::GetMessagePos() ); 
    ScreenToClient(&pos);

    // Get indexes of the first and last visible items in 
    // the listview control.
    int index = m_myListCtrl.GetTopIndex();
    int last_visible_index = index + m_myListCtrl.GetCountPerPage();
    if (last_visible_index > m_myListCtrl.GetItemCount())
        last_visible_index = m_myListCtrl.GetItemCount();

    // Loop until number visible items has been reached.
    while (index <= last_visible_index)
    {
        // Get the bounding rectangle of an item. If the mouse
        // location is within the bounding rectangle of the item,
        // you know you have found the item that was being clicked.
        CRect r;
        m_myListCtrl.GetItemRect(index, &r, LVIR_BOUNDS);
        if (r.PtInRect(pia->ptAction))
        {
            UINT flag = LVIS_SELECTED | LVIS_FOCUSED;
            m_myListCtrl.SetItemState(index, flag, flag);
            break;
        }

        // Get the next item in listview control.
        index++;
    }
}
```

  
##  <a name="getitemspacing"></a>  CListCtrl::GetItemSpacing  
 現在のリスト ビュー コントロール内の項目間の間隔を計算します。  
  
```  
BOOL GetItemSpacing(
    BOOL fSmall,   
    int* pnHorzSpacing,   
    int* pnVertSpacing) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fSmall`|アイテム間の間隔を取得する対象のビュー。 指定`true`小さいアイコン ビューに、または`false`アイコンの表示にします。|  
|[出力] `pnHorzSpacing`|項目間の左右の間隔が含まれています。|  
|[出力] `pnVertSpacing`|項目間の上下の間隔が含まれています。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_GETITEMSPACING](http://msdn.microsoft.com/library/windows/desktop/bb761051) Windows SDK で説明するメッセージ。  
  
##  <a name="getitemstate"></a>  CListCtrl::GetItemState  
 リスト ビューの項目の状態を取得します。  
  
```  
UINT GetItemState(
    int nItem,  
    UINT nMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 状態を取得する項目のインデックス。  
  
 `nMask`  
 返されるアイテムの状態のうちフラグを指定するマスクです。  
  
### <a name="return-value"></a>戻り値  
 項目指定の一覧については、状態フラグを表示します。  
  
### <a name="remarks"></a>コメント  
 項目の状態がで指定された、**状態**のメンバー、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) Windows SDK」の説明に従って、構造体します。 指定または項目の状態を変更するときに、**対象**メンバーを変更するビットを指定します。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetTopIndex](#gettopindex)です。  
  
##  <a name="getitemtext"></a>  CListCtrl::GetItemText  
 リスト ビューの項目またはサブ項目のテキストを取得します。  
  
```  
int GetItemText(
    int nItem,  
    int nSubItem,  
    LPTSTR lpszText,  
    int nLen) const; 
 
CString GetItemText(
    int nItem,  
    int nSubItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 テキストを取得する項目のインデックス。  
  
 `nSubItem`  
 テキストを取得するサブ項目を指定します。  
  
 `lpszText`  
 項目のテキストを受信する文字列へのポインター。  
  
 `nLen`  
 バッファーの長さを指す`lpszText`です。  
  
### <a name="return-value"></a>戻り値  
 返すバージョン`int`取得した文字列の長さを返します。  
  
 返すバージョン、`CString`項目のテキストを返します。  
  
### <a name="remarks"></a>コメント  
 場合`nSubItem`0 の場合は、場合、この関数が項目ラベルを取得`nSubItem`はサブ項目のテキストを取得、0 以外の場合。 サブアイテムの引数の詳細については、の説明を参照してください、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) Windows SDK 内の構造。  
  
##  <a name="getnextitem"></a>  CListCtrl::GetNextItem  
 一覧の検索では、項目を持つ、指定されたプロパティおよび指定した項目に指定されたリレーションシップを持つことを表示します。  
  
```  
int GetNextItem(
    int nItem,  
    int nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 指定したフラグに一致する最初の項目を検索する場合は-1、検索を開始する項目のインデックス。 指定した項目自体は、検索から除外されます。  
  
 `nFlags`  
 指定した項目および要求された項目の状態を要求された項目の幾何学的関係します。 幾何学的関係には、これらの値のいずれかを指定できます。  
  
- `LVNI_ABOVE` 指定した項目上にある項目を検索します。  
  
- `LVNI_ALL` インデックス (既定値) を使用して後続の項目を検索します。  
  
- `LVNI_BELOW` 指定した項目の下にある項目を検索します。  
  
- `LVNI_TOLEFT` 指定した項目の左側にあるアイテムを検索します。  
  
- `LVNI_TORIGHT` 指定した項目の右側にあるアイテムを検索します。  
  
 状態は、0、またはこれらの値の 1 つ以上であることができます。  
  
- `LVNI_DROPHILITED` 項目が、`LVIS_DROPHILITED`状態フラグを設定します。  
  
- `LVNI_FOCUSED` 項目が、`LVIS_FOCUSED`状態フラグを設定します。  
  
- `LVNI_SELECTED` 項目が、`LVIS_SELECTED`状態フラグを設定します。  
  
 項目があるないと、指定した状態フラグのセットのすべて、次のアイテムを検索が続行されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、次の項目またはそれ以外の場合に-1 のインデックス。  
  
##  <a name="getnextitemindex"></a>  CListCtrl::GetNextItemIndex  
 プロパティの指定したセットが現在のリスト ビュー コントロール内の項目のインデックスを取得します。  
  
```  
BOOL GetNextItemIndex(
    PLVITEMINDEX pItemIndex,   
    int nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力、出力] `pItemIndex`|ポインター、[記述](http://msdn.microsoft.com/library/windows/desktop/bb774762)検索開始位置となる項目を記述する構造体または内のフラグに一致する最初の項目を検索する場合は-1、`nFlags`パラメーター。<br /><br /> このメソッドが成功した場合、`LVITEMINDEX`構造体は、検索で見つかった項目を示します。|  
|[入力] `nFlags`|検索を実行する方法を指定するフラグのビットごとの組み合わせ (OR)。<br /><br /> 検索は、インデックス、状態、またはターゲット項目の外観に依存するか、項目、ターゲット項目の物理的な位置で指定された、`pItemIndex`パラメーター。 詳細については、次を参照してください。、`flags`内のパラメーター、 [LVM_GETNEXTITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761059)メッセージ。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 呼び出し元が割り当てと設定のメンバーを担当する、`LVITEMINDEX`構造体を指す、`pItemIndex`パラメーター。  
  
 このメソッドは、送信、 [LVM_GETNEXTITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761059) Windows SDK で説明するメッセージ。  
  
##  <a name="getnextselecteditem"></a>  CListCtrl::GetNextSelectedItem  
 識別されるリスト項目のインデックスを取得`pos`を設定し、 *pos*を**位置**値。  
  
```  
int GetNextSelectedItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**を以前の呼び出しによって返される値`GetNextSelectedItem`または`GetFirstSelectedItemPosition`です。 値は、この呼び出しによって次の位置に更新されます。  
  
### <a name="return-value"></a>戻り値  
 によって識別されるリスト項目のインデックス`pos`です。  
  
### <a name="remarks"></a>コメント  
 使用することができます`GetNextSelectedItem`への呼び出しに最初の位置を確立する場合は、順方向の反復ループで`GetFirstSelectedItemPosition`です。  
  
 確認する必要があります、**位置**値が無効です。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
 次のコード サンプルは、この関数の使用法を示しています。    
  
```cpp  
        POSITION pos = m_myListCtrl.GetFirstSelectedItemPosition();
        if (pos == NULL)
        {
            TRACE(_T("No items were selected!\n"));
        }
        else
        {
            while (pos)
            {
                int nItem = m_myListCtrl.GetNextSelectedItem(pos);
                TRACE(_T("Item %d was selected!\n"), nItem);
                // you could do your own processing on nItem here
            }
        }
```

  
##  <a name="getnumberofworkareas"></a>  CListCtrl::GetNumberOfWorkAreas  
 リスト ビュー コントロールの作業領域の現在の数を取得します。  
  
```  
UINT GetNumberOfWorkAreas() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この時点では使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetNumberOfWorkAreas](http://msdn.microsoft.com/library/windows/desktop/bb774988)Windows SDK で説明されている。  
  
### <a name="example"></a>例    
  
```cpp  
        UINT i, uCount = m_myListCtrl.GetNumberOfWorkAreas();
        LPRECT lpRects = (LPRECT) malloc(uCount*sizeof(RECT));

        if (lpRects != NULL)
        {
            // Dump all of the work area dimensions.
            m_myListCtrl.GetWorkAreas(uCount, lpRects);

            for (i=0; i < uCount; i++)
            {
                TRACE(_T("Work area %d; left = %d, top = %d, right = %d, ")
                    _T("bottom = %d\r\n"),
                    i, lpRects[i].left, lpRects[i].top, lpRects[i].right, 
                    lpRects[i].bottom);
            }

            free(lpRects);
        }
        else
        {
            TRACE(_T("Couldn't allocate enough memory!"));   
        }

```

  
##  <a name="getoutlinecolor"></a>  CListCtrl::GetOutlineColor  
 リスト ビュー コントロールの境界線の色を取得します。  
  
```  
COLORREF GetOutlineColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)外枠の色を含む構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETOUTLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761065)メッセージ、Windows SDK で説明します。  
  
##  <a name="getorigin"></a>  CListCtrl::GetOrigin  
 リスト ビュー コントロールの現在のビューの原点を取得します。  
  
```  
BOOL GetOrigin(LPPOINT lpPoint) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPoint`  
 アドレス、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)ビューの基準を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。 ただし、コントロールは、レポート ビューでは場合に、戻り値常に 0 です。  
  
##  <a name="getselectedcolumn"></a>  CListCtrl::GetSelectedColumn  
 リスト コントロールで現在選択されている列のインデックスを取得します。  
  
```  
UINT GetSelectedColumn() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択した列のインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETSELECTEDCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb761067)メッセージ、Windows SDK で説明します。  
  
##  <a name="getselectedcount"></a>  CListCtrl::GetSelectedCount  
 リスト ビュー コントロールで選択した項目の数を取得します。  
  
```  
UINT GetSelectedCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロールで選択した項目の数。  
  
### <a name="example"></a>例    
  
```cpp  
        UINT i, uSelectedCount = m_myListCtrl.GetSelectedCount();
        int  nItem = -1;

        // Update all of the selected items.
        if (uSelectedCount > 0)
        {
            for (i=0; i < uSelectedCount; i++)
            {
                nItem = m_myListCtrl.GetNextItem(nItem, LVNI_SELECTED);
                ASSERT(nItem != -1);
                m_myListCtrl.Update(nItem); 
            }
        }
```

  
##  <a name="getselectionmark"></a>  CListCtrl::GetSelectionMark  
 リスト ビュー コントロールの選択のマークを取得します。  
  
```  
int GetSelectionMark();
```  
  
### <a name="return-value"></a>戻り値  
 0 から始まる選択マーク、または選択マークがない場合は-1。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetSelectionMark](http://msdn.microsoft.com/library/windows/desktop/bb774998)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

```cpp  
    // Set the selection mark to the first item only if no other item is 
    // selected.
    if (m_myListCtrl.GetSelectionMark() == -1)
        m_myListCtrl.SetSelectionMark(0);
```

  
##  <a name="getstringwidth"></a>  CListCtrl::GetStringWidth  
 指定された文字列のすべてを表示するために必要な最小列幅を決定します。  
  
```  
int GetStringWidth(LPCTSTR lpsz) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 幅を確認する null で終わる文字列のアドレス。  
  
### <a name="return-value"></a>戻り値  
 幅 (ピクセル単位) を指す文字列の`lpsz`します。  
  
### <a name="remarks"></a>コメント  
 返される幅では、コントロールの現在のフォントと列の余白が小さいアイコンの幅ではありませんが考慮されます。  
  
### <a name="example"></a>例  

```cpp  
        CString strColumn;
        int nWidth;

        // Insert six columns in the list view control. Make the width of
        // the column be the width of the column header plus 50%.
        for (int i = 0; i < 6; i++)
        {
            strColumn.Format(_T("column %d"), i);
            nWidth = 3*m_myListCtrl.GetStringWidth(strColumn)/2;
            m_myListCtrl.InsertColumn(i, strColumn, LVCFMT_LEFT, nWidth);
        }
```

  
##  <a name="getsubitemrect"></a>  CListCtrl::GetSubItemRect  
 リスト ビュー コントロール内の項目の外接する四角形を取得します。  
  
```  
BOOL GetSubItemRect(
    int iItem,  
    int iSubItem,  
    int nArea,  
    CRect& ref);
```  
  
### <a name="parameters"></a>パラメーター  
 *iItem*  
 サブアイテムの親項目のインデックス。  
  
 *iSubItem*  
 サブアイテムの 1 から始まるインデックス。  
  
 *nArea*  
 取得するには、(リスト ビューのサブアイテム) の外接する四角形の部分を決定します。 外接する四角形の部分 (アイコン、ラベル、またはその両方) は、次の値の 1 つ以上のビットごとの OR 演算子を適用することによって指定されます。  
  
- `LVIR_BOUNDS` アイコンとラベルを含む、アイテム全体の外接する四角形を返します。  
  
- `LVIR_ICON` アイコンまたは小さいアイコンに外接する四角形を返します。  
  
- `LVIR_LABEL` アイコンとラベルを含む、アイテム全体の外接する四角形を返します。 これと同じ`LVIR_BOUNDS`です。  
  
 `ref`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)サブアイテムの座標を格納しているオブジェクトの外接する四角形。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetSubItemRect](http://msdn.microsoft.com/library/windows/desktop/bb775004)Windows SDK で説明されている。  
  
##  <a name="gettextbkcolor"></a>  CListCtrl::GetTextBkColor  
 リスト ビュー コントロールのテキストの背景色を取得します。  
  
```  
COLORREF GetTextBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色を指定するために使用する 32 ビット値です。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::SetTextBkColor](#settextbkcolor)です。  
  
##  <a name="gettextcolor"></a>  CListCtrl::GetTextColor  
 リスト ビュー コントロールのテキストの色を取得します。  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 色を指定するために使用する 32 ビット値です。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::SetTextColor](#settextcolor)です。  
  
##  <a name="gettileinfo"></a>  CListCtrl::GetTileInfo  
 リスト ビュー コントロールでのタイルに関する情報を取得します。  
  
```  
BOOL GetTileInfo(PLVTILEINFO pti) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pti*  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774766)タイル情報を受け取る構造です。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETTILEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761081)メッセージ、Windows SDK で説明します。  
  
##  <a name="gettileviewinfo"></a>  CListCtrl::GetTileViewInfo  
 タイル ビューでリスト ビュー コントロールに関する情報を取得します。  
  
```  
BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ptvi`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774768)取得した情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETTILEVIEWINFO](http://msdn.microsoft.com/library/windows/desktop/bb761083)メッセージ、Windows SDK で説明します。  
  
##  <a name="gettooltips"></a>  CListCtrl::GetToolTips  
 リスト ビュー コントロールを使用してツールヒントを表示するツール ヒント コントロールを取得します。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](ctooltipctrl-class.md)リスト コントロールで使用するオブジェクト。 場合、[作成](#create)メンバー関数は、スタイルを使用して**LVS_NOTOOLTIPS**、ツールヒントを使用しないと**NULL**が返されます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LVM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb761085)Windows SDK で説明されている。 MFC 実装の`GetToolTips`を返します、`CToolTipCtrl`ツールヒント コントロールへのハンドルではなく、リスト コントロールで使用されるオブジェクト。  
  
### <a name="example"></a>例  

```cpp  
        CToolTipCtrl* pTip = m_myListCtrl.GetToolTips();
        if (NULL != pTip)
        {
            pTip->UpdateTipText(_T("I'm a list view!"), &m_myListCtrl,
                IDD_MYLISTCTRL);
        }
```

  
##  <a name="gettopindex"></a>  CListCtrl::GetTopIndex  
 リスト ビューまたはレポート ビューで、最上位に表示される項目のインデックスを取得します。  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 最上位に表示される項目のインデックス。  
  
### <a name="example"></a>例  

 
```cpp  
        // Make sure the focus is set to the list view control.
        m_myListCtrl.SetFocus();

        // Select all of the items that are completely visible.
        int n = m_myListCtrl.GetTopIndex();
        int nLast = n + m_myListCtrl.GetCountPerPage();

        for (; n < nLast; n++)
        {
            m_myListCtrl.SetItemState(n, LVIS_SELECTED, LVIS_SELECTED);
            ASSERT(m_myListCtrl.GetItemState(n, LVIS_SELECTED) == LVIS_SELECTED); 
        }
```

  
##  <a name="getview"></a>  CListCtrl::GetView  
 リスト ビュー コントロールのビューを取得します。  
  
```  
DWORD GetView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロールの現在のビューです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_GETVIEW](http://msdn.microsoft.com/library/windows/desktop/bb761091)メッセージ、Windows SDK で説明します。  
  
##  <a name="getviewrect"></a>  CListCtrl::GetViewRect  
 リスト ビュー コントロール内のすべての項目の外接する四角形を取得します。  
  
```  
BOOL GetViewRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 アドレス、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 リスト ビューは、ビューのアイコンまたは小さいアイコンの表示でなければなりません。  
  
##  <a name="getworkareas"></a>  CListCtrl::GetWorkAreas  
 リスト ビュー コントロールの現在の作業領域を取得します。  
  
```  
void GetWorkAreas(
    int nWorkAreas,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nWorkAreas`  
 数`RECT`構造体に含まれている、*中華人民共和国*配列。  
  
 `prc`  
 配列へのポインター`RECT`構造体 (または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト) を受信するリスト ビュー コントロールの作業領域です。 これらの構造体の値は、クライアント座標でです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_GetWorkAreas](http://msdn.microsoft.com/library/windows/desktop/bb775024)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetNumberOfWorkAreas](#getnumberofworkareas)です。  
  
##  <a name="hasgroup"></a>  CListCtrl::HasGroup  
 リスト ビュー コントロールに、指定されたグループがあるかどうかを判断します。  
  
```  
BOOL HasGroup(int iGroupId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iGroupId`  
 要求されているグループの識別子。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_HASGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761097)メッセージ、Windows SDK で説明します。  
  
##  <a name="hittest"></a>  CListCtrl::HitTest  
 指定した位置にある場合は、どのリスト ビューの項目を決定します。  
  
```  
int HitTest(LVHITTESTINFO* pHitTestInfo) const;  
  
int HitTest(
    CPoint pt,  
    UINT* pFlags = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pHitTestInfo`  
 アドレス、**持ち**ヒット テストする位置を格納する構造体がヒット テストの結果に関する情報を受け取ります。  
  
 `pt`  
 テストする点です。  
  
 `pFlags`  
 テストの結果に関する情報を受け取る整数へのポインター。 説明を参照してください、**フラグ**のメンバー、[持ち](http://msdn.microsoft.com/library/windows/desktop/bb774754)Windows SDK 内の構造。  
  
### <a name="return-value"></a>戻り値  
 指定された位置にある項目のインデックス`pHitTestInfo`存在する場合、またはそれ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
 使用することができます、 `LVHT_ABOVE`、 `LVHT_BELOW`、 `LVHT_TOLEFT`、および`LVHT_TORIGHT`の構造体の値**フラグ**メンバーにリスト ビュー コントロールの内容をスクロールするかどうかを確認します。 これらのフラグの 2 つの結合できます、たとえば、上とクライアント領域の左側には、位置は場合。  
  
 テストすることができます、 **LVHT_ONITEM**の構造体の値**フラグ**メンバーに指定された位置がリスト ビューの項目の上かどうかを確認します。 この値のビットごとの OR 操作は、 `LVHT_ONITEMICON`、 `LVHT_ONITEMLABEL`、および`LVHT_ONITEMSTATEICON`の構造体の値**フラグ**メンバー。  
  
### <a name="example"></a>例  

```cpp  
void CListCtrlDlg::OnRClick(NMHDR* pNMHDR, LRESULT* pResult)
{
    LPNMITEMACTIVATE pia = (LPNMITEMACTIVATE)pNMHDR;
    CPoint point(pia->ptAction);

    // Select the item the user clicked on.
    UINT uFlags;
    int nItem = m_myListCtrl.HitTest(point, &uFlags);

    if (uFlags & LVHT_ONITEMLABEL)
    {
        m_myListCtrl.SetItem(nItem, 0, LVIF_STATE, NULL, 0, LVIS_SELECTED, 
            LVIS_SELECTED, 0);
    }

    *pResult = 0;
}
```

  
##  <a name="insertcolumn"></a>  CListCtrl::InsertColumn  
 リスト ビュー コントロールに新しい列を挿入します。  
  
```  
int InsertColumn(
    int nCol,  
    const LVCOLUMN* pColumn);

 
int InsertColumn(
    int nCol,  
    LPCTSTR lpszColumnHeading,  
    int nFormat = LVCFMT_LEFT,  
    int nWidth = -1,  
    int nSubItem = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCol`  
 新しい列のインデックス。  
  
 `pColumn`  
 アドレス、 **LVCOLUMN**新しい列の属性を格納する構造体。  
  
 *lpszColumnHeading*  
 列の見出しを含む文字列のアドレスです。  
  
 `nFormat`  
 列の配置を指定する整数。 これらの値のいずれかです:**どれ**、 **LVCFMT_RIGHT**、または**LVCFMT_CENTER**です。  
  
 `nWidth`  
 ピクセル単位で、列の幅。 このパラメーターが-1 の場合、列の幅は設定されていません。  
  
 `nSubItem`  
 列に関連付けられているサブ項目のインデックス。 このパラメーターが-1 の場合は、サブ項目の列に関連付けはありません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、新しい列またはそれ以外の場合は-1 のインデックス。  
  
### <a name="remarks"></a>コメント  
 リスト ビュー コントロールの左端の列は、左揃えにする必要があります。  
  
 [LVCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743)構造には、レポート ビューの列の属性が含まれています。 列に関する情報を受信するも使用されます。 この構造体は、Windows SDK の説明です。  
  
##  <a name="insertgroup"></a>  CListCtrl::InsertGroup  
 グループをリスト ビュー コントロールに挿入します。  
  
```  
LRESULT InsertGroup(
    int index,  
    PLVGROUP pgrp);
```  
  
### <a name="parameters"></a>パラメーター  
 *index*  
 グループを挿入する項目のインデックス。  
  
 `pgrp`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)を追加するグループを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 操作が失敗した場合は、-1 または、グループが追加される項目のインデックスを返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_INSERTGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761103)メッセージ、Windows SDK で説明します。  
  
##  <a name="insertgroupsorted"></a>  CListCtrl::InsertGroupSorted  
 グループの順序付きリストに指定されたグループを挿入します。  
  
```  
LRESULT InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStructInsert*  
 ポインター、[された](http://msdn.microsoft.com/library/windows/desktop/bb774756)を挿入するグループを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_INSERTGROUPSORTED](http://msdn.microsoft.com/library/windows/desktop/bb761105)メッセージ、Windows SDK で説明します。  
  
##  <a name="insertitem"></a>  CListCtrl::InsertItem  
 リスト ビュー コントロールに項目を挿入します。  
  
```  
int InsertItem(const LVITEM* pItem);

 
int InsertItem(
    int nItem,  
    LPCTSTR lpszItem);

 
int InsertItem(
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage);

 
int InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    UINT nState,  
    UINT nStateMask,  
    int nImage,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 ポインター、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760)を Windows SDK」の説明に従って、項目の属性を指定します。  
  
 `nItem`  
 挿入する項目のインデックス。  
  
 `lpszItem`  
 項目のラベルを表す文字列のアドレスまたは`LPSTR_TEXTCALLBACK`場合は、項目は、コールバック項目。 コールバック項目については、次を参照してください。 [CListCtrl::GetCallbackMask](#getcallbackmask)です。  
  
 `nImage`  
 項目のイメージのインデックスまたは`I_IMAGECALLBACK`場合は、項目は、コールバック項目。 コールバック項目については、次を参照してください。 [CListCtrl::GetCallbackMask](#getcallbackmask)です。  
  
 `nMask`  
 `nMask`どの項目を指定します。 パラメーターとして渡される属性は無効です。 いずれかまたはで説明したマスクの値の[LVITEM 構造体](http://msdn.microsoft.com/library/windows/desktop/bb774760)Windows SDK に含まれています。 有効な値は、ビットごとの OR 演算子と組み合わせることができます。  
  
 `nState`  
 項目の状態、状態イメージとイメージのオーバーレイを示します。 Windows SDK のトピックを参照して[LVITEM 構造](http://msdn.microsoft.com/library/windows/desktop/bb774760)詳細については、[リスト ビュー項目の状態](http://msdn.microsoft.com/library/windows/desktop/bb774733)有効なフラグの一覧についてはします。  
  
 `nStateMask`  
 状態のメンバーのビットを取得または変更されることを示します。 参照してください[LVITEM 構造](http://msdn.microsoft.com/library/windows/desktop/bb774760)詳細については、Windows SDK に含まれています。  
  
 `lParam`  
 アイテムに関連付けられている 32 ビット アプリケーションに固有の値。 設定する必要がありますこのパラメーターが指定されている場合、`nMask`属性`LVIF_PARAM`です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、新しいアイテムまたはそれ以外の場合に-1 のインデックス。  
  
### <a name="remarks"></a>コメント  
 呼び出し元がこのメソッドが発生する可能性があります、**呼び出す**コントロール ウィンドウに送信されるメッセージ。 コントロールに関連付けられたメッセージ ハンドラーは、特定の条件下で項目のテキストを設定できない可能性があります (ウィンドウ スタイルを使用してなど**LVS_OWNERDRAW**)。 これらの条件の詳細についてを参照してください[呼び出す](http://msdn.microsoft.com/library/windows/desktop/bb761107)Windows SDK に含まれています。  
  
### <a name="example"></a>例  

```cpp  
        CString strText;
        int nColumnCount = m_myListCtrl.GetHeaderCtrl()->GetItemCount();

        // Insert 10 items in the list view control.
        for (int i = 0; i < 10; i++)
        {
            strText.Format(TEXT("item %d"), i);

            // Insert the item, select every other item.
            m_myListCtrl.InsertItem(LVIF_TEXT | LVIF_STATE, i, strText, 
                (i % 2) == 0 ? LVIS_SELECTED : 0, LVIS_SELECTED, 0, 0);

            // Initialize the text of the subitems.
            for (int j = 1; j < nColumnCount; j++)
            {
                strText.Format(TEXT("sub-item %d %d"), i, j);
                m_myListCtrl.SetItemText(i, j, strText);
            }
        }
```

  
##  <a name="insertmarkhittest"></a>  CListCtrl::InsertMarkHitTest  
 指定したポイントに最も近いカーソル位置を取得します。  
  
```  
int InsertMarkHitTest(
    LPPOINT pPoint,  
    LPLVINSERTMARK lvim) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pPoint`  
 ポインター、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)リスト コントロールのクライアント領域と相対的、ヒット テストを含む構造体を調整します。  
  
 `lvim`  
 ポインター、 [LVINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774758)をパラメーターで定義されている座標に最も近い挿入ポイントを指定します。  
  
### <a name="return-value"></a>戻り値  
 最も近い位置にカーソルを指定したポイントします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_INSERTMARKHITTEST](http://msdn.microsoft.com/library/windows/desktop/bb761131)メッセージ、Windows SDK で説明します。  
  
##  <a name="isgroupviewenabled"></a>  CListCtrl::IsGroupViewEnabled  
 リスト ビュー コントロールのグループの表示が有効になっているかどうかを判断します。  
  
```  
BOOL IsGroupViewEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**グループの表示が有効になっている場合または**FALSE**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_ISGROUPVIEWENABLED](http://msdn.microsoft.com/library/windows/desktop/bb761133)メッセージ、Windows SDK で説明します。  
  
##  <a name="isitemvisible"></a>  CListCtrl::IsItemVisible  
 現在のリスト ビュー コントロール内の指定した項目を表示するかどうかを示します。  
  
```  
BOOL IsItemVisible(int index) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `index`|現在のリスト ビュー コントロール内の項目の 0 から始まるインデックス。|  
  
### <a name="return-value"></a>戻り値  
 `true` 指定した項目が表示されている、それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_ISITEMVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb761135) Windows SDK で説明するメッセージ。  
  
##  <a name="mapidtoindex"></a>  CListCtrl::MapIDToIndex  
 現在のリスト ビュー コントロール内のアイテムの一意の ID をインデックスにマップします。  
  
```  
UINT MapIDToIndex(UINT id) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `id`|項目の一意の ID。|  
  
### <a name="return-value"></a>戻り値  
 指定した ID の現在のインデックス  
  
### <a name="remarks"></a>コメント  
 リスト ビュー コントロールは、インデックスを使用して内部的に項目を追跡します。 コントロールの有効期間中にインデックスが変更できるので、問題が発生することができます。 リスト ビュー コントロールは ID を持つ項目をタグ付け、項目が作成され、リスト ビュー コントロールの有効期間中に一意性を保証するためにこの ID を使用することができます。  
  
 マルチ スレッド環境で、インデックスが保証されるは、バック グラウンド スレッドではなく、リスト ビュー コントロールをホストしているスレッドのみに注意してください。  
  
 このメソッドは、送信、 [LVM_MAPIDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761137) Windows SDK で説明するメッセージ。  
  
##  <a name="mapindextoid"></a>  CListCtrl::MapIndexToID  
 現在のリスト ビュー コントロール内の項目のインデックスを一意の ID にマップします。  
  
```  
UINT MapIndexToID(UINT index) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `index`|項目の 0 から始まるインデックス。|  
  
### <a name="return-value"></a>戻り値  
 指定した項目の一意の ID。  
  
### <a name="remarks"></a>コメント  
 リスト ビュー コントロールは、インデックスを使用して内部的に項目を追跡します。 コントロールの有効期間中にインデックスが変更できるので、問題が発生することができます。 リスト ビュー コントロールは ID を持つ項目をタグ付け、項目が作成されたとき。 この ID を使用して、リスト ビュー コントロールの有効期間の特定の項目にアクセスすることができます。  
  
 マルチ スレッド環境で、インデックスが保証されるは、バック グラウンド スレッドではなく、リスト ビュー コントロールをホストしているスレッドのみに注意してください。  
  
 このメソッドは、送信、 [LVM_MAPINDEXTOID](http://msdn.microsoft.com/library/windows/desktop/bb761139) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_listCtrl`、つまり現在のリスト ビュー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。    
  
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>例  
 次のコード例を示しています、`MapIndexToID`メソッドです。 このコード例の前のセクションでは、レポート ビューの"ClientID"および"Grade"をという 2 つの列を表示するリスト ビュー コントロールを作成しました。 次の例では、識別番号を各リスト ビュー項目のインデックスをマップし、各 id 番号のインデックスを取得します。 最後に、例では、元のインデックスが取得されたかどうかを報告します。    
  
```cpp  
    // MapIndexToID
    int iCount = m_listCtrl.GetItemCount();
    UINT nId = 0;
    UINT nIndex = 0;
    for (int iIndexOriginal = 0; iIndexOriginal < iCount; iIndexOriginal++)
    {
        // Map index to ID.
        nId = m_listCtrl.MapIndexToID((UINT)iIndexOriginal);

        // Map ID to index.
        nIndex = m_listCtrl.MapIDToIndex(nId);

        if (nIndex != (UINT)(iIndexOriginal))
        {
            CString str;
            str.Format(_T("Mapped index (%d) is not equal to original index (%d)"),
                nIndex, (UINT)(iIndexOriginal));
            AfxMessageBox(str);
            return;
        }
    }
    AfxMessageBox(_T("The mapped indexes and original indexes are equal."), 
        MB_ICONINFORMATION);
```

  
##  <a name="movegroup"></a>  CListCtrl::MoveGroup  
 リスト ビュー コントロールの 0 から始まるインデックスを指定された、指定されたグループに移動します。  
  
```  
LRESULT MoveGroup(
    int iGroupId,  
    int toIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `iGroupId`  
 移動するグループの識別子。  
  
 `toIndex`  
 グループを移動する 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_MOVEGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761141)メッセージ、Windows SDK で説明します。  
  
##  <a name="moveitemtogroup"></a>  CListCtrl::MoveItemToGroup  
 指定した項目を指定されたグループに移動します。  
  
```  
void MoveItemToGroup(
    int idItemFrom,  
    int idGroupTo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `idItemFrom`  
 移動する項目のインデックス。  
  
 [入力] `idGroupTo`  
 グループの識別子を項目は移動されます。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  現在このメソッドは実装されません。  
  
 このメソッドは、の機能をエミュレート、 [LVM_MOVEITEMTOGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761143)メッセージ、Windows SDK で説明します。  
  
##  <a name="redrawitems"></a>  CListCtrl::RedrawItems  
 項目の範囲を再描画するリスト ビュー コントロールを強制します。  
  
```  
BOOL RedrawItems(
    int nFirst,  
    int nLast);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFirst`  
 再描画する最初の項目のインデックス。  
  
 `nLast`  
 再描画する最後の項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した項目がない実際に再描画、リスト ビュー ウィンドウを受け取るまで、`WM_PAINT`メッセージ。 すぐに再描画呼び出し、Windows[と](http://msdn.microsoft.com/library/windows/desktop/dd145167)関数の後、この関数を使用します。  
  
##  <a name="removeallgroups"></a>  CListCtrl::RemoveAllGroups  
 リスト ビュー コントロールからすべてのグループを削除します。  
  
```  
void RemoveAllGroups();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_REMOVEALLGROUPS](http://msdn.microsoft.com/library/windows/desktop/bb761147)メッセージ、Windows SDK で説明します。  
  
##  <a name="removegroup"></a>  CListCtrl::RemoveGroup  
 リスト ビュー コントロールから、指定されたグループを削除します。  
  
```  
LRESULT RemoveGroup(int iGroupId);
```  
  
### <a name="parameters"></a>パラメーター  
 `iGroupId`  
 削除するグループの識別子。  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、成功した場合、グループまたは-1 のインデックスを返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_REMOVEGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761149)メッセージ、Windows SDK で説明します。  
  
##  <a name="scroll"></a>  CListCtrl::Scroll  
 リスト ビュー コントロールの内容をスクロールします。  
  
```  
BOOL Scroll(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 A `CSize` (ピクセル単位)、水平方向および垂直のスクロールの量を指定するオブジェクト。 **Y**のメンバー `size` (ピクセル単位) のリスト ビュー コントロールの行の高さで割った値が結果の行の数によって、コントロールがスクロールされる基準とします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="setbkcolor"></a>  CListCtrl::SetBkColor  
 リスト ビュー コントロールの背景色を設定します。  
  
```  
BOOL SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>パラメーター  
 `cr`  
 背景色を設定するにまたは`CLR_NONE`いない背景色の値。 背景色でリスト ビュー コントロールの再描画が大幅に背景色を持たないものよりも高速です。 詳細については、次を参照してください。 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  

 
```cpp  
        // Use the 3D button face color for the background.
        COLORREF crBkColor = ::GetSysColor(COLOR_3DFACE);
        m_myListCtrl.SetBkColor(crBkColor);
        ASSERT(m_myListCtrl.GetBkColor() == crBkColor);
```

  
##  <a name="setbkimage"></a>  CListCtrl::SetBkImage  
 リスト ビュー コントロールの背景イメージを設定します。  
  
```  
BOOL SetBkImage(LVBKIMAGE* plvbkImage);
 
BOOL SetBkImage(
    HBITMAP hbm,  
    BOOL fTile = TRUE,  
    int xOffsetPercent = 0,  
    int yOffsetPercent = 0);
 
BOOL SetBkImage(
    LPTSTR pszUrl,  
    BOOL fTile = TRUE,  
    int xOffsetPercent = 0,  
    int yOffsetPercent = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `plvbkImage`  
 アドレス、**格納されて**新しい背景イメージ情報を保持します。  
  
 `hbm`  
 ビットマップへのハンドルします。  
  
 `pszUrl`  
 A **NULL**-背景画像の URL を表す文字列を終了します。  
  
 *fTile*  
 イメージが、リスト ビュー コントロールの背景に並べて表示する場合は 0 以外。それ以外の場合 0 を返します。  
  
 *xOffsetPercent*  
 リスト ビュー コントロールの原点から、イメージの左端のピクセル単位のオフセット。  
  
 *yOffsetPercent*  
 リスト ビュー コントロールの原点からのイメージの上端からのピクセル単位のオフセット。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外を返します。 または 0 それ以外の場合。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  `CListCtrl::SetBkImage` OLE COM 機能を利用、OLE ライブラリを使用する前に初期化する必要があります`SetBkImage`です。 アプリケーションが初期化されたときに COM ライブラリを初期化し、アプリケーションの終了時に、ライブラリを初期化することをお勧めします。 これは、自動的に ActiveX テクノロジ、OLE オートメーション、OLE リンク/埋め込み、または ODBC と DAO 操作の MFC でを実行するアプリケーションを使用します。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetBkImage](#getbkimage)です。  
  
##  <a name="setcallbackmask"></a>  CListCtrl::SetCallbackMask  
 リスト ビュー コントロールのコールバック マスクを設定します。  
  
```  
BOOL SetCallbackMask(UINT nMask);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMask`  
 コールバック マスクの新しい値。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  

 
```cpp  
    // Set the callback mask so that only the selected and focused states
    // are stored for each item.
    m_myListCtrl.SetCallbackMask(LVIS_SELECTED|LVIS_FOCUSED);
    ASSERT(m_myListCtrl.GetCallbackMask() == 
        (LVIS_SELECTED|LVIS_FOCUSED));
```


##  <a name="setcheck"></a>  CListCtrl::SetCheck  
 リスト コントロール項目の状態の画像が表示されているかどうかを判断します。  
  
```  
BOOL SetCheck(
    int nItem,  
    BOOL fCheck = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 リスト コントロール項目の 0 から始まるインデックス。  
  
 `fCheck`  
 項目の状態の画像するかどうか表示されているかどうかを指定します。 既定では、*して*は**TRUE**状態の画像が表示されるとします。 場合`fCheck`は**FALSE**は表示されません。  
  
### <a name="return-value"></a>戻り値  
 項目がオンの場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="example"></a>例  

 
```cpp  
        int nCount = m_myListCtrl.GetItemCount();
        BOOL fCheck = FALSE;

        // Set the check state of every other item to TRUE and 
        // all others to FALSE.
        for (int i = 0; i < nCount; i++)
        {
            m_myListCtrl.SetCheck(i, fCheck);
            ASSERT((m_myListCtrl.GetCheck(i) && fCheck) || 
                (!m_myListCtrl.GetCheck(i) && !fCheck));
            fCheck = !fCheck;
        }
```

  
##  <a name="setcolumn"></a>  CListCtrl::SetColumn  
 リスト ビューの列の属性を設定します。  
  
```  
BOOL SetColumn(
    int nCol,  
    const LVCOLUMN* pColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCol`  
 属性を設定する列のインデックス。  
  
 `pColumn`  
 アドレス、 [LVCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743)属性、Windows SDK」の説明に従って、新しい列を含む構造体。 構造体の**マスク**のどの列属性を設定するメンバーを指定します。 場合、**マスク**メンバーを指定します、`LVCF_TEXT`値構造体の**pszText**メンバーは、null で終わる文字列と構造体のアドレス**cchTextMax**メンバーは無視されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetColumn](#getcolumn)です。  
  
##  <a name="setcolumnorderarray"></a>  CListCtrl::SetColumnOrderArray  
 リスト ビュー コントロールの列順序 (左右から) を設定します。  
  
```  
BOOL SetColumnOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `piArray`  
 (左から右) のリスト ビュー コントロール内の列のインデックス値を格納するバッファーへのポインター。 バッファーは、リスト ビュー コントロール内の列の合計数を格納するのに十分な大きさである必要があります。  
  
 `iCount`  
 リスト ビュー コントロール内の列の数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetColumnOrderArray](http://msdn.microsoft.com/library/windows/desktop/bb775072)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetColumnOrderArray](#getcolumnorderarray)です。  
  
##  <a name="setcolumnwidth"></a>  CListCtrl::SetColumnWidth  
 レポート ビューまたはリスト ビュー内の列の幅を変更します。  
  
```  
BOOL SetColumnWidth(
    int nCol,  
    int cx);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCol`  
 幅を設定する対象の列のインデックス。 リスト ビューで、このパラメーターは 0 を指定する必要があります。  
  
 `cx`  
 新しい列の幅。 いずれかになります**LVSCW_AUTOSIZE**または**LVSCW_AUTOSIZE_USEHEADER**」の説明に従って、 [LVM_SETCOLUMNWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb761163) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="setextendedstyle"></a>  かざして  
 リスト ビュー コントロールの現在の拡張スタイルを設定します。  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwNewStyle`  
 リスト ビュー コントロールで使用する拡張スタイルの組み合わせ。 わかりやすいのこれらのスタイルの一覧を表示するには、次を参照してください。、[リスト ビューのスタイルの拡張](http://msdn.microsoft.com/library/windows/desktop/bb774732)Windows SDK のトピックです。  
  
### <a name="return-value"></a>戻り値  
 前の組み合わせは、リスト ビュー コントロールで使用されるスタイルを拡張します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetExtendedListViewStyle](http://msdn.microsoft.com/library/windows/desktop/bb775076)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

 
```cpp  
    // Allow the header controls item to be movable by the user.
    m_myListCtrl.SetExtendedStyle
        (m_myListCtrl.GetExtendedStyle()|LVS_EX_HEADERDRAGDROP);
```

  
##  <a name="setgroupinfo"></a>  CListCtrl::SetGroupInfo  
 現在のリスト ビュー コントロールの指定したグループを説明する情報を設定します。  
  
```  
int SetGroupInfo(
    int iGroupId,  
    PLVGROUP pgrp);
```  
  
### <a name="parameters"></a>パラメーター  
 `iGroupId`  
 情報を設定、グループの識別子。  
  
 `pgrp`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774769)設定情報を格納する構造体。 呼び出し元は、この構造体を割り当てると、そのメンバーを設定します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、グループの IDそれ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [LVM_SETGROUPINFO](http://msdn.microsoft.com/library/windows/desktop/bb761167) Windows SDK で説明するメッセージ。  
  
##  <a name="setgroupmetrics"></a>  CListCtrl::SetGroupMetrics  
 リスト ビュー コントロールのグループのメトリックを設定します。  
  
```  
void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroupMetrics`  
 ポインター、 [LVGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb774752)を設定するグループのメトリック情報を含む構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb761168)メッセージ、Windows SDK で説明します。  
  
##  <a name="sethotcursor"></a>  CListCtrl::SetHotCursor  
 リスト ビュー コントロールのホット トラッキングが有効になっているときに使用するカーソルを設定します。  
  
```  
HCURSOR SetHotCursor(HCURSOR hc);
```  
  
### <a name="parameters"></a>パラメーター  
 *ホスト コント ローラー*  
 ホット カーソルを表すために使用するカーソル リソースへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 リスト ビュー コントロールで使用されている以前のホット カーソル リソースへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetHotCursor](http://msdn.microsoft.com/library/windows/desktop/bb775082)Windows SDK で説明されている。  
  
 カーソルが、リスト ビューの項目を通過ホバー時の選択範囲が有効になっているときにだけ表示ホット カーソルが表示されます。 ホバー時の選択範囲が有効になって、 **LVS_EX_TRACKSELECT**拡張スタイル。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetHotCursor](#gethotcursor)です。  
  
##  <a name="sethotitem"></a>  CListCtrl::SetHotItem  
 リスト ビュー コントロールの現在のホット項目を設定します。  
  
```  
int SetHotItem(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 ホット アイテムとして設定する項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 前のホット アイテムの 0 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetHotItem](http://msdn.microsoft.com/library/windows/desktop/bb775083)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetHotItem](#gethotitem)です。  
  
##  <a name="sethovertime"></a>  CListCtrl::SetHoverTime  
 リスト ビュー コントロールの現在のホバー時の時刻を設定します。  
  
```  
DWORD SetHoverTime(DWORD dwHoverTime = (DWORD)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwHoverTime*  
 新しい遅延が選択されている前に、アイテムの上、マウス カーソルを合わせて (ミリ秒)。 既定値は渡された場合、時刻は既定のホバー時の時間に設定されます。  
  
### <a name="return-value"></a>戻り値  
 前のホバー時の時間 (ミリ秒単位)。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetHoverTime](http://msdn.microsoft.com/library/windows/desktop/bb775084)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetHoverTime](#gethovertime)です。  
  
##  <a name="seticonspacing"></a>  CListCtrl::SetIconSpacing  
 リスト ビュー コントロール内のアイコンの間隔を設定します。  
  
```  
CSize SetIconSpacing(
    int cx,  
    int cy);  
  
CSize SetIconSpacing(CSize size);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 間の間隔 (ピクセル単位)、x 軸上のアイコン。  
  
 `cy`  
 間の間隔 (ピクセル単位)、y 軸上のアイコン。  
  
 `size`  
 A`CSize`アイコン間の x 軸および y 軸の間隔 (ピクセル単位) を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)アイコンの間隔の以前の値を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetIconSpacing](http://msdn.microsoft.com/library/windows/desktop/bb775085)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

 
```cpp  
    // Leave lots of space between icons.
    m_myListCtrl.SetIconSpacing(CSize(100, 100));
```

  
##  <a name="setimagelist"></a>  CListCtrl::SetImageList  
 リスト ビュー コントロールにイメージ リストを割り当てます。  
  
```  
CImageList* SetImageList(
    CImageList* pImageList,  
    int nImageListType);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 割り当てるイメージ リストへのポインター。  
  
 `nImageListType`  
 イメージ リストの種類です。 これらの値のいずれかを指定できます。  
  
- `LVSIL_NORMAL` 大きいアイコンのイメージ リスト。  
  
- `LVSIL_SMALL` 小さいアイコンのイメージ リスト。  
  
- `LVSIL_STATE` 状態のイメージのイメージ リスト。  
  
### <a name="return-value"></a>戻り値  
 直前のイメージ リストへのポインター。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetImageList](#getimagelist)です。  
  
##  <a name="setinfotip"></a>  CListCtrl::SetInfoTip  
 ツールヒントのテキストを設定します。  
  
```  
BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);
```  
  
### <a name="parameters"></a>パラメーター  
 *plvInfoTip*  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774764)を設定する情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb761180)メッセージ、Windows SDK で説明します。  
  
##  <a name="setinsertmark"></a>  CListCtrl::SetInsertMark  
 定義済みの位置にカーソルを設定します。  
  
```  
BOOL SetInsertMark(LPLVINSERTMARK lvim);
```  
  
### <a name="parameters"></a>パラメーター  
 `lvim`  
 ポインター、 [LVINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774758)カーソルを設定する場所を指定する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、または**FALSE**それ以外の場合。 **FALSE**場合に返されるサイズで、`cbSize`のメンバー、 **LVINSERTMARK**構造が、構造体の実際のサイズと等しくないかが現在のビューには、挿入ポイントの場合は適用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb761182)メッセージ、Windows SDK で説明します。  
  
##  <a name="setinsertmarkcolor"></a>  CListCtrl::SetInsertMarkColor  
 挿入ポイントの色を設定します。  
  
```  
COLORREF SetInsertMarkColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)カーソルを設定する色を指定する構造体。  
  
### <a name="return-value"></a>戻り値  
 返します、 **COLORREF**以前の色を含む構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761184)メッセージ、Windows SDK で説明します。  
  
##  <a name="setitem"></a>  CListCtrl::SetItem  
 リスト ビューの一部またはすべてを項目の属性を設定します。  
  
```  
BOOL SetItem(const LVITEM* pItem);

 
BOOL SetItem(
    int nItem,  
    int nSubItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam);

 
BOOL SetItem(
    int nItem,  
    int nSubItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam,  
    int nIndent);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 アドレス、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) Windows SDK」の説明に従って、新しい項目を格納する構造体の属性です。 構造体の**iItem**と**iSubItem**項目またはサブ項目、および構造体のメンバーが識別**マスク**メンバーを設定する属性を指定します。 詳細については、**マスク**、メンバーを参照してください、**解説**です。  
  
 `nItem`  
 属性を設定するアイテムのインデックス。  
  
 `nSubItem`  
 設定する属性を持つは、サブ項目のインデックス。  
  
 `nMask`  
 (「解説」を参照してください) を設定する属性を指定します。  
  
 `lpszItem`  
 項目のラベルを指定する null で終わる文字列のアドレスです。  
  
 `nImage`  
 イメージ リスト内の項目のイメージのインデックス。  
  
 `nState`  
 (「解説」を参照してください) を変更する状態の値をを指定します。  
  
 `nStateMask`  
 (「解説」を参照してください) を変更するどの状態を指定します。  
  
 `lParam`  
 アイテムに関連する 32 ビット アプリケーションに固有値。  
  
 `nIndent`  
 インデントのピクセル単位の幅。 場合`nIndent`が小さいシステム定義の最小幅よりも新しい幅がシステム定義の最小値に設定  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **IItem**と**iSubItem**のメンバー、 **LVITEM**構造および`nItem`と`nSubItem`パラメーターのアイテムの識別し、subitem が属性では、設定します。  
  
 **マスク**のメンバー、 **LVITEM**構造および`nMask`パラメーターは、アイテムを指定の属性を設定するのには。  
  
- `LVIF_TEXT` **PszText**メンバーまたは`lpszItem`パラメーターが null で終わる文字列のアドレス以外の場合は、 **cchTextMax**メンバーは無視されます。  
  
- `LVIF_STATE` **対象**メンバーまたは`nStateMask`パラメーターを指定する項目の状態を変更して、**状態**メンバーまたは`nState`パラメーターには、これらの状態の値が含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::HitTest](#hittest)です。  
  
##  <a name="setitemcount"></a>  CListCtrl::SetItemCount  
 多数のアイテムを追加するには、リスト ビュー コントロールを準備します。  
  
```  
void SetItemCount(int nItems);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItems`  
 コントロールを含む最終的には項目の数。  
  
### <a name="remarks"></a>コメント  
 仮想リスト ビュー コントロールの項目数を設定するを参照してください。 [CListCtrl::SetItemCountEx](#setitemcountex)です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetItemCount](http://msdn.microsoft.com/library/windows/desktop/bb775093)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

 
```cpp  
        CString str;

        // Add 1024 items to the list view control.
        m_myListCtrl.SetItemCount(1024);

        for (int i = 0; i < 1024; i++)
        {
            str.Format(TEXT("item %d"), i);
            m_myListCtrl.InsertItem(i, str);
        }
```

  
##  <a name="setitemcountex"></a>  CListCtrl::SetItemCountEx  
 仮想リスト ビュー コントロールの項目数を設定します。  
  
```  
BOOL SetItemCountEx(
    int iCount,  
    DWORD dwFlags = LVSICF_NOINVALIDATEALL);
```  
  
### <a name="parameters"></a>パラメーター  
 `iCount`  
 コントロールを含む最終的には項目の数。  
  
 `dwFlags`  
 項目数にリセットした後、リスト ビュー コントロールの動作を指定します。 この値は、次の組み合わせにすることができます。  
  
- **LVSICF_NOINVALIDATEALL**ビューの影響を受ける項目している場合を除き、リスト ビュー コントロールが再描画されません。 これが既定値です。  
  
- **LVSICF_NOSCROLL**ユーザーはアイテム数が変更時に、リスト ビュー コントロールにはスクロールの位置は変更されません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetItemCountEx](http://msdn.microsoft.com/library/windows/desktop/bb775095)、」の説明に従って Windows SDKand のみの呼び出すことは仮想一覧表示します。  
  
### <a name="example"></a>例  

 
```cpp  
        CString str;

        // Add 1024 items to the list view control.

        // Force my virtual list view control to allocate 
        // enough memory for my 1024 items.
        m_myVirtualListCtrl.SetItemCountEx(1024, LVSICF_NOSCROLL|
            LVSICF_NOINVALIDATEALL);

        for (int i = 0; i < 1024; i++)
        {
            str.Format(TEXT("item %d"), i);
            m_myVirtualListCtrl.InsertItem(i, str);
        }
```

  
##  <a name="setitemdata"></a>  CListCtrl::SetItemData  
 指定した項目に関連付けられている 32 ビット アプリケーションに固有の値を設定`nItem`です。  
  
```  
BOOL SetItemData(int nItem, DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 データが含まれるを設定するリスト項目のインデックス。  
  
 `dwData`  
 アイテムに関連する 32 ビット値です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この値は、 **lParam**のメンバー、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) Windows SDK」の説明に従って、構造体します。  
  
### <a name="example"></a>例  

 
```cpp  
    // Set the data of each item to be equal to its index.
    for (int i = 0; i < m_myListCtrl.GetItemCount(); i++)
    {
        m_myListCtrl.SetItemData(i, i);
    }
```

  
##  <a name="setitemindexstate"></a>  CListCtrl::SetItemIndexState  
 現在のリスト ビュー コントロールの項目の状態を設定します。  
  
```  
BOOL SetItemIndexState(
    PLVITEMINDEX pItemIndex,   
    DWORD dwState,   
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pItemIndex`|ポインター、[記述](http://msdn.microsoft.com/library/windows/desktop/bb774762)項目を記述する構造体。 呼び出し元は、この構造体を割り当てると、そのメンバーを設定します。|  
|[入力] `dwState`|アイテムを設定する状態のビットごとの組み合わせは[ビュー項目の状態を一覧表示](http://msdn.microsoft.com/library/windows/desktop/bb774733)です。 リセットには 0 または状態を設定する 1 つを指定します。|  
|[入力] `dwMask`|指定された状態の有効なビットのマスク、`dwState`パラメーター。 ビットごとの組み合わせ (OR) を指定[ビュー項目の状態を一覧表示](http://msdn.microsoft.com/library/windows/desktop/bb774733)です。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 詳細については、`dwState`パラメーターを参照してください[リスト ビュー項目の状態](http://msdn.microsoft.com/library/windows/desktop/bb774733)です。  
  
 詳細については、`dwMask`パラメーターを参照してください、`stateMask`のメンバー、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760)構造体。  
  
 このメソッドは、送信、 [LVM_SETITEMINDEXSTATE](http://msdn.microsoft.com/library/windows/desktop/bb761190) Windows SDK で説明するメッセージ。  
  
##  <a name="setitemposition"></a>  CListCtrl::SetItemPosition  
 リスト ビュー コントロール内の指定位置に項目を移動します。  
  
```  
BOOL SetItemPosition(
    int nItem,  
    POINT pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 位置を設定する項目のインデックス。  
  
 `pt`  
 A[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)アイテムの左上隅のビュー内の新しい位置を指定する構造体を調整します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コントロールは、アイコンまたは小さいアイコンの表示にする必要があります。  
  
 リスト ビュー コントロールがある場合、`LVS_AUTOARRANGE`スタイル、リスト ビューは、アイテムの位置を設定した後に配置されます。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetItemPosition](#getitemposition)です。  
  
##  <a name="setitemstate"></a>  CListCtrl::SetItemState  
 リスト ビュー コントロール内の項目の状態を変更します。  
  
```  
BOOL SetItemState(
    int nItem,  
    LVITEM* pItem);

 
BOOL SetItemState(
    int nItem,  
    UINT nState,  
    UINT nMask);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 状態を設定する項目のインデックス。  
  
 `pItem`  
 アドレス、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) Windows SDK」の説明に従って、構造体します。 構造体の**対象**どの状態ビットを変更、および構造体のメンバーを指定**状態**メンバーには、これらのビットの新しい値が含まれています。 他のメンバーは無視されます。  
  
 `nState`  
 状態ビットの新しい値。 使用可能な値の一覧は、次を参照してください。 [CListCtrl::GetNextItem](#getnextitem)と[LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760)状態のメンバーです。  
  
 `nMask`  
 指定するどの状態を変更するビット マスク。 この値の対象のメンバーに対応、 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760)構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 項目の"state"は、アイテムの有効性を示す、ユーザーの操作、またはそれ以外の場合、項目の状態が反映されますを示す値です。 リスト ビュー コントロールでは、ユーザーが項目を選択するとなどのいくつかの状態ビットを変更します。 その他の状態ビットを無効にするか、アイテムを非表示にするのにまたはオーバーレイ イメージまたは状態の画像を指定するアプリケーションを変更します。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetTopIndex](#gettopindex)です。  
  
##  <a name="setitemtext"></a>  CListCtrl::SetItemText  
 リスト ビューの項目またはサブ項目のテキストを変更します。  
  
```  
BOOL SetItemText(
    int nItem,  
    int nSubItem,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 テキストを設定する項目のインデックス。  
  
 `nSubItem`  
 項目のラベルを設定するサブ項目、または 0 のインデックス。  
  
 `lpszText`  
 新しい項目のテキストを表す文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは使用できません LVS_OWNERDATA ウィンドウ スタイルを含むコントロールで (実際には、これにより、アサーション デバッグ ビルドで)。 このリスト コントロール スタイルの詳細については、次を参照してください。[リスト ビュー コントロールの概要](http://msdn.microsoft.com/library/windows/desktop/bb774735)です。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::InsertItem](#insertitem)です。  
  
##  <a name="setoutlinecolor"></a>  CListCtrl::SetOutlineColor  
 場合、リスト ビュー コントロールの境界線の色を設定、 [LVS_EX_BORDERSELECT](http://msdn.microsoft.com/library/windows/desktop/bb774739)拡張ウィンドウ スタイルが設定されています。  
  
```  
COLORREF SetOutlineColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 新しい[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)外枠の色を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 前の**COLORREF**外枠の色を含む構造体  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETOUTLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761200)メッセージ、Windows SDK で説明します。  
  
##  <a name="setselectedcolumn"></a>  CListCtrl::SetSelectedColumn  
 リスト ビュー コントロールの選択した列を設定します。  
  
```  
LRESULT SetSelectedColumn(int iCol);
```  
  
### <a name="parameters"></a>パラメーター  
 *iCol*  
 選択するのには、列のインデックス。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETSELECTEDCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb761202)メッセージ、Windows SDK で説明します。  
  
##  <a name="setselectionmark"></a>  CListCtrl::SetSelectionMark  
 リスト ビュー コントロールの選択のマークを設定します。  
  
```  
int SetSelectionMark(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 複数の選択範囲の最初の項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 前の選択マーク、または選択マークが存在しなかった場合は-1。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetSelectionMark](http://msdn.microsoft.com/library/windows/desktop/bb775112)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetSelectionMark](#getselectionmark)です。  
  
##  <a name="settextbkcolor"></a>  CListCtrl::SetTextBkColor  
 リスト ビュー コントロールでテキストの背景色を設定します。  
  
```  
BOOL SetTextBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>パラメーター  
 `cr`  
 A **COLORREF**新しいテキストの背景色を指定します。 詳細については、次を参照してください。 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  

 
```cpp  
        // Use the 3D button face color for the background.
        COLORREF crBkColor = ::GetSysColor(COLOR_3DFACE);
        m_myListCtrl.SetTextBkColor(crBkColor);
        ASSERT(m_myListCtrl.GetTextBkColor() == crBkColor);
```

  
##  <a name="settextcolor"></a>  CListCtrl::SetTextColor  
 リスト ビュー コントロールのテキストの色を設定します。  
  
```  
BOOL SetTextColor(COLORREF cr);
```  
  
### <a name="parameters"></a>パラメーター  
 `cr`  
 A **COLORREF**新しいテキストの色を指定します。 詳細については、次を参照してください。 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  

 
```cpp  
    // Use the window text color for
    // the item text of the list view control.
    COLORREF crTextColor = ::GetSysColor(COLOR_WINDOWTEXT);
    m_myListCtrl.SetTextColor(crTextColor);
    ASSERT(m_myListCtrl.GetTextColor() == crTextColor);
```

  
##  <a name="settileinfo"></a>  CListCtrl::SetTileInfo  
 リスト ビュー コントロールのタイルの情報を設定します。  
  
```  
BOOL SetTileInfo(PLVTILEINFO pti);
```  
  
### <a name="parameters"></a>パラメーター  
 *pti*  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774766)を設定する情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETTILEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761210)メッセージ、Windows SDK で説明します。  
  
##  <a name="settileviewinfo"></a>  CListCtrl::SetTileViewInfo  
 タイル ビューでは、リスト ビュー コントロールを使用する情報を設定します。  
  
```  
BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptvi`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/bb774768)設定情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETTILEVIEWINFO](http://msdn.microsoft.com/library/windows/desktop/bb761212)メッセージ、Windows SDK で説明します。  
  
##  <a name="settooltips"></a>  CListCtrl::SetToolTips  
 リスト ビュー コントロールがツールヒントの表示に使用するツール ヒント コントロールを設定します。  
  
```  
CToolTipCtrl* SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndTip`  
 ポインター、`CToolTipCtrl`リスト コントロールを使用するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](ctooltipctrl-class.md)コントロールによって使用されていたヒントを含むオブジェクトまたは`NULL`ツールヒントを使用していません以前場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[LVM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb761216)Windows SDK で説明されている。  
  
 ツール ヒントを使用できません、`LVS_NOTOOLTIPS`スタイルを作成するとき、`CListCtrl`オブジェクト。  
  
##  <a name="setview"></a>  CListCtrl::SetView  
 リスト ビュー コントロールのビューを設定します。  
  
```  
DWORD SetView(int iView);
```  
  
### <a name="parameters"></a>パラメーター  
 *iView*  
 選択するビューです。  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、成功した場合、1 または-1 を返します。 たとえば、ビューが有効でない場合に-1 が返されます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SETVIEW](http://msdn.microsoft.com/library/windows/desktop/bb761220)メッセージ、Windows SDK で説明します。  
  
##  <a name="setworkareas"></a>  CListCtrl::SetWorkAreas  
 リスト ビュー コントロールにアイコンを表示する範囲を設定します。  
  
```  
void SetWorkAreas(
    int nWorkAreas,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nWorkAreas`  
 数`RECT`構造体 (または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト) によって示される配列に`lpRect`です。  
  
 `lpRect`  
 配列のアドレス`RECT`構造体 (または`CRect`オブジェクト)、リスト ビュー コントロールの新しい作業領域を指定します。 クライアント座標では、これらの領域を指定する必要があります。 このパラメーターが場合**NULL**、作業領域は、コントロールのクライアント領域に設定されます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SetWorkAreas](http://msdn.microsoft.com/library/windows/desktop/bb775128)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

 
```cpp  
    // Remove all working areas.
    m_myListCtrl.SetWorkAreas(0, NULL);
```

  
##  <a name="sortgroups"></a>  CListCtrl::SortGroups  
 リスト ビュー コントロール内の ID でグループを並べ替えるには、アプリケーション定義の比較関数を使用します。  
  
```  
BOOL SortGroups(
    PFNLVGROUPCOMPARE _pfnGroupCompare,  
    LPVOID _plv);
```  
  
### <a name="parameters"></a>パラメーター  
 `_pfnGroupCompare`  
 グループの比較関数へのポインター。  
  
 `_plv`  
 Void ポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`true` を返します。それ以外の場合は、`false` を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [LVM_SORTGROUPS](http://msdn.microsoft.com/library/windows/desktop/bb761225)メッセージ、Windows SDK で説明します。  
  
##  <a name="sortitems"></a>  CListCtrl::SortItems  
 アプリケーション定義の比較関数を使用してリスト ビュー項目を並べ替えます。  
  
```  
BOOL SortItems(
    PFNLVCOMPARE pfnCompare,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pfnCompare`  
 アプリケーション定義の比較関数のアドレス。  
  
 並べ替え操作では、次の 2 つのリスト項目の相対順序を決定する必要があるたびに、比較関数を呼び出します。 比較関数は、クラスの静的メンバーまたは任意のクラスのメンバーではないスタンドアロン関数のいずれかにする必要があります。  
  
 [入力] `dwData`  
 比較関数に渡されるアプリケーション定義の値。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合、メソッドが成功しました。それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、新しいシーケンスを反映するように各項目のインデックスを変更します。  
  
 比較関数`pfnCompare`は次の形式があります。  
  
```  
int CALLBACK CompareFunc(LPARAM lParam1,
    LPARAM lParam2,
    LPARAM lParamSort);
```  
場合は、2 つ目の前に指定する必要があります最初の項目、比較関数は、負の値を返す必要がありますが、正の値を使用している場合は、最初の項目が 2 番目、または場合は 0 に従う必要があります、2 つの項目が等しい。  
  
 `lParam1`パラメーターは、32 ビット値の比較、最初の項目に関連付けられていると、`lParam2`パラメーターは、2 番目の項目に関連付けられている値。 これらで指定された値、`lParam`項目のメンバー [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760)リストに挿入されたときにします。 `lParamSort`と同じパラメーターは、`dwData`値。  
  
 このメソッドは、送信、 [LVM_SORTITEMS](http://msdn.microsoft.com/library/windows/desktop/bb761227) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次は、単純な比較関数によって並べ替えられる項目の結果を`lParam`値。  
  
```cpp  
// Sort items by associated lParam
int CALLBACK CListCtrlDlg::MyCompareProc(LPARAM lParam1, LPARAM lParam2, 
    LPARAM lParamSort)
{
    UNREFERENCED_PARAMETER(lParamSort);
return (int)(lParam1 - lParam2);
}
```
  
```cpp  
// Sort the items by passing in the comparison function.
void CListCtrlDlg::Sort()
{
    m_myListCtrl.SortItems(&CListCtrlDlg::MyCompareProc, 0);
}
```
  
##  <a name="sortitemsex"></a>  CListCtrl::SortItemsEx  
 アプリケーション定義の比較関数を使用して、現在のリスト ビュー コントロールの項目を並べ替えます。  
  
```  
BOOL SortItemsEx(
    PFNLVCOMPARE pfnCompare,   
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pfnCompare`|アプリケーション定義の比較関数のアドレス。<br /><br /> 並べ替え操作では、次の 2 つのリスト項目の相対順序を決定する必要があるたびに、比較関数を呼び出します。 比較関数は、クラスの静的メンバーまたは任意のクラスのメンバーではないスタンドアロン関数のいずれかにする必要があります。|  
|[入力] `dwData`|アプリケーション定義の値は、比較関数に渡されます。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、新しいシーケンスを反映するように各項目のインデックスを変更します。  
  
 比較関数`pfnCompare`は次の形式があります。  
  
```  
int CALLBACK CompareFunc(LPARAM lParam1,
    LPARAM lParam2,
    LPARAM lParamSort);
```  
このメッセージはのように、 [LVM_SORTITEMS](http://msdn.microsoft.com/library/windows/desktop/bb761227)、比較関数に渡される情報の種類を除く。 [LVM_SORTITEMS](http://msdn.microsoft.com/library/windows/desktop/bb761227)、`lParam1`と`lParam2`を比較する項目の値です。 [LVM_SORTITEMSEX](http://msdn.microsoft.com/library/windows/desktop/bb761228)、`lParam1`を比較する最初の項目の現在のインデックスと`lParam2`は、2 番目の項目の現在のインデックス。 送信することができます、 [LVM_GETITEMTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761055)メッセージ、その項目に関する詳細情報を取得します。  
  
 場合は、2 つ目の前に指定する必要があります最初の項目、比較関数は、負の値を返す必要がありますが、正の値を使用している場合は、最初の項目が 2 番目、または場合は 0 に従う必要があります、2 つの項目が等しい。  
  
> [!NOTE]
>  並べ替えの処理中に、リスト ビューの内容は安定性はします。 コールバック関数は、任意にメッセージを送信、リスト ビュー コントロール以外の場合[LVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb774953)結果は予測できません。  
  
 このメソッドは、送信、 [LVM_SORTITEMSEX](http://msdn.microsoft.com/library/windows/desktop/bb761228) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例の変数を定義`m_listCtrl`、つまり現在のリスト ビュー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。  
  
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>例  
 次のコード例を示しています、`SortItemEx`メソッドです。 このコード例の前のセクションでは、レポート ビューの"ClientID"および"Grade"をという 2 つの列を表示するリスト ビュー コントロールを作成しました。 次のコード例では、"Grade"列の値を使用して、テーブルを並べ替えます。  
  

```cpp  
// The ListCompareFunc() method is a global function used by SortItemEx().
int CALLBACK ListCompareFunc(
                             LPARAM lParam1, 
                             LPARAM lParam2, 
                             LPARAM lParamSort)
{
    CListCtrl* pListCtrl = (CListCtrl*) lParamSort;
    CString    strItem1 = pListCtrl->GetItemText(static_cast<int>(lParam1), 1);
    CString    strItem2 = pListCtrl->GetItemText(static_cast<int>(lParam2), 1)
    int x1 = _tstoi(strItem1.GetBuffer());
    int x2 = _tstoi(strItem2.GetBuffer());
    int result = 0;
    if ((x1 - x2) < 0)
        result = -1;
    else if ((x1 - x2) == 0)
        result = 0;
    else
        result = 1;

    return result;
}

void CCListCtrl_s2Dlg::OnBnClickedButton1()
{
    // SortItemsEx
    m_listCtrl.SortItemsEx( ListCompareFunc, (LPARAM)&m_listCtrl );
}
```

  
##  <a name="subitemhittest"></a>  CListCtrl::SubItemHitTest  
 指定された位置に存在する場合は、どのリスト ビューの項目を決定します。  
  
```  
int SubItemHitTest(LPLVHITTESTINFO pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInfo`  
 ポインター、[持ち](http://msdn.microsoft.com/library/windows/desktop/bb774754)構造体。  
  
### <a name="return-value"></a>戻り値  
 項目またはサブ項目、(存在する場合) をテストする、または-1 それ以外の場合の 1 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 マクロの動作を実装して[ListView_SubItemHitTest](http://msdn.microsoft.com/library/windows/desktop/bb775135)Windows SDK で説明されている。  
  
### <a name="example"></a>例  

```cpp  
void CListCtrlDlg::OnDblClk(NMHDR* pNMHDR, LRESULT* pResult)
{
    UNREFERENCED_PARAMETER(pResult);
LPNMITEMACTIVATE pia = (LPNMITEMACTIVATE)pNMHDR;
    LVHITTESTINFO lvhti;

    // Clear the subitem text the user clicked on.
    lvhti.pt = pia->ptAction;
    m_myListCtrl.SubItemHitTest(&lvhti);

    if (lvhti.flags & LVHT_ONITEMLABEL)
    {
        m_myListCtrl.SetItemText(lvhti.iItem, lvhti.iSubItem, NULL);
    }
}
```

  
##  <a name="update"></a>  CListCtrl::Update  
 指定した項目を再描画するリスト ビュー コントロールが強制的に`nItem`です。  
  
```  
BOOL Update(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 項目のインデックスを更新します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数がある場合も、リスト ビュー コントロールを並べ替えます、`LVS_AUTOARRANGE`スタイル。  
  
### <a name="example"></a>例  
  例を参照して[CListCtrl::GetSelectedCount](#getselectedcount)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル rowlist で](../../visual-cpp-samples.md)   
 [CWnd クラス](cwnd-class.md)   
 [階層図](../hierarchy-chart.md)   
 [CImageList クラス](cimagelist-class.md)

