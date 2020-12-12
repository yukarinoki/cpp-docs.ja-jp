---
description: '詳細情報: CJumpList クラス'
title: CJumpList クラス
ms.date: 03/27/2019
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
ms.openlocfilehash: 07e896c5b3a205a44850d45dcc4876103a48f2fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236907"
---
# <a name="cjumplist-class"></a>CJumpList クラス

は、 `CJumpList` タスクバーのアイコンを右クリックしたときに表示されるショートカットの一覧です。

## <a name="syntax"></a>構文

```
class CJumpList;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CJumpList::CJumpList](#cjumplist)|`CJumpList` オブジェクトを構築します。|
|[CJumpList:: ~ CJumpList](#_dtorcjumplist)|`CJumpList` オブジェクトを破棄します。|

|名前|説明|
|----------|-----------------|
|[CJumpList:: AbortList](#abortlist)|コミットせずにリスト構築トランザクションを中止します。|
|[CJumpList:: AddDestination](#adddestination)|オーバーロードされます。 リストに宛先を追加します。|
|[CJumpList:: AddKnownCategory](#addknowncategory)|既知のカテゴリを一覧に追加します。|
|[CJumpList:: AddTask](#addtask)|オーバーロードされます。 標準のタスクカテゴリに項目を追加します。|
|[CJumpList:: AddTasks](#addtasks)|標準のタスクカテゴリに項目を追加します。|
|[CJumpList:: AddTaskSeparator](#addtaskseparator)|タスク間に区切り記号を追加します。|
|[CJumpList:: ClearAll](#clearall)|これまでにの現在のインスタンスに追加されているすべてのタスクと変換先を削除し `CJumpList` ます。|
|[CJumpList:: ClearAllDestinations](#clearalldestinations)|これまでにの現在のインスタンスに追加されているすべての変換先を削除 `CJumpList` します。|
|[CJumpList:: CommitList](#commitlist)|リスト構築トランザクションを終了し、報告されたリストを関連するストア (この場合はレジストリ) にコミットします。|
|[CJumpList:: GetDestinationList](#getdestinationlist)|宛先リストへのインターフェイスポインターを取得します。|
|[CJumpList:: GetMaxSlots](#getmaxslots)|呼び出し元アプリケーションのターゲットメニューに表示できるカテゴリヘッダーを含む、項目の最大数を取得します。|
|[CJumpList:: GetRemovedItems](#getremoveditems)|削除された変換先を表す項目の配列を返します。|
|[CJumpList:: InitializeList](#initializelist)|リスト構築トランザクションを開始します。|
|[CJumpList:: SetAppID](#setappid)|ビルドされるリストのアプリケーションユーザーモデル ID を設定します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxadv

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a> CJumpList:: ~ CJumpList

`CJumpList` オブジェクトを破棄します。

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a> CJumpList:: AbortList

コミットせずにリスト構築トランザクションを中止します。

```cpp
void AbortList();
```

### <a name="remarks"></a>解説

このメソッドを呼び出すと、を呼び出さずに破棄する場合と同じ効果があり `CJumpList` `CommitList` ます。

## <a name="cjumplistadddestination"></a><a name="adddestination"></a> CJumpList:: AddDestination

リストに宛先を追加します。

```
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,
    LPCTSTR strDestinationPath);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellItem* pShellItem);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellLink* pShellLink);
```

### <a name="parameters"></a>パラメーター

*lpcszCategoryName*<br/>
カテゴリ名を指定します。 指定したカテゴリが存在しない場合は、作成されます。

*strDestinationPath*<br/>
ターゲットファイルへのパスを指定します。

*strCategoryName 区分名*<br/>
カテゴリ名を指定します。 指定したカテゴリが存在しない場合は、作成されます。

*pShellItem*<br/>
追加する対象を表すシェル項目を指定します。

*pShellLink*<br/>
追加するターゲットを表すシェルリンクを指定します。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

のインスタンスは、 `CJumpList` 内部的に追加された変換先を蓄積し、でそれらをコミットし `CommitList` ます。

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a> CJumpList:: AddKnownCategory

既知のカテゴリを一覧に追加します。

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>パラメーター

*category*<br/>
既知のカテゴリの種類を指定します。 KDC_RECENT、KDC_KNOWN のいずれかになります。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

既知のカテゴリは、頻繁に使用されるカテゴリです。これは、を利用するすべてのアプリケーション `SHAddToRecentDocs` (または、シェルがいくつかのシナリオでアプリケーションの代わりに呼び出すときに間接的に使用されます) に対して自動的に計算されます。

## <a name="cjumplistaddtask"></a><a name="addtask"></a> CJumpList:: AddTask

標準のタスクカテゴリに項目を追加します。

```
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,
    LPCTSTR strCommandLineArgs,
    LPCTSTR strTitle,
    LPCTSTR strIconLocation,
    int iIconIndex);

BOOL AddTask(IShellLink* pShellLink);
```

### <a name="parameters"></a>パラメーター

*strTargetExecutablePath*<br/>
ターゲットタスクのパスを指定します。

*strCommandLineArgs*<br/>
*Strtargetexecutablepath* によって指定された実行可能ファイルのコマンドライン引数を指定します。

*strTitle*<br/>
対象の一覧に表示されるタスクの名前。

*strIconLocation*<br/>
コピー先の一覧にタイトルと共に表示されるアイコンの位置。

*iIconIndex*<br/>
アイコンインデックス。

*pShellLink*<br/>
追加するタスクを表すシェルリンク。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

のインスタンスは、 `CJumpList` 指定されたタスクを蓄積し、の間にそれらを対象のリストに追加し `CommitList` ます。 タスク項目は、アプリケーションの [宛先] メニューの下部にあるカテゴリに表示されます。 このカテゴリは、UI に入力されると、他のすべてのカテゴリに優先します。

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a> CJumpList:: AddTasks

標準のタスクカテゴリに項目を追加します。

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>パラメーター

*pObjectCollection*<br/>
追加するタスクのコレクション。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

CJumpList のインスタンスは、指定されたタスクを蓄積し、の間にそれらを対象のリストに追加し `CommitList` ます。 タスク項目は、アプリケーションの [宛先] メニューの下部にあるカテゴリに表示されます。 このカテゴリは、UI に入力されると、他のすべてのカテゴリに優先します。

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a> CJumpList:: AddTaskSeparator

タスク間に区切り記号を追加します。

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>戻り値

成功した場合は0以外、それ以外の場合は0。

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a> CJumpList::CJumpList

`CJumpList` オブジェクトを構築します。

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>パラメーター

*bAutoCommit コミット*<br/>
このパラメーターが FALSE の場合、リストはデストラクターで自動的にコミットされません。

## <a name="cjumplistclearall"></a><a name="clearall"></a> CJumpList:: ClearAll

これまでにの現在のインスタンスに追加されているすべてのタスクと変換先を削除し `CJumpList` ます。

```cpp
void ClearAll();
```

### <a name="remarks"></a>解説

このメソッドは、すべてのデータと内部インターフェイスをクリアし、解放します。

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a> CJumpList:: ClearAllDestinations

これまでに CJumpList の現在のインスタンスに追加されているすべての変換先を削除します。

```cpp
void ClearAllDestinations();
```

### <a name="remarks"></a>解説

この関数を呼び出します。これまでに、宛先リストの構築の現在のセッションに追加されたすべての変換先を削除して、他の変換先を追加する必要がある場合に呼び出します。 内部 `ICustomDestinationList` が初期化されている場合は、そのままになります。

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a> CJumpList:: CommitList

リスト構築トランザクションを終了し、報告されたリストを関連するストア (この場合はレジストリ) にコミットします。

```
BOOL CommitList();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

コミットはアトミックです。 コミットが失敗すると、エラーが返されます。  が呼び出されると、削除された `CommitList` 項目の現在のリストがクリーンアップされます。 このメソッドを呼び出すと、アクティブなリスト構築トランザクションがないようにオブジェクトがリセットされます。 リストを更新するには、を `BeginList` 再度呼び出す必要があります。

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a> CJumpList:: GetDestinationList

宛先リストへのインターフェイスポインターを取得します。

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

ジャンプリストが初期化されていない場合、またはコミットまたは中止された場合、戻り値は NULL になります。

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a> CJumpList:: GetMaxSlots

呼び出し元アプリケーションのターゲットメニューに表示できるカテゴリヘッダーを含む、項目の最大数を取得します。

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

アプリケーションでは、この値まで結合された複数の項目およびカテゴリヘッダーのみを報告できます。 `AppendCategory`、 `AppendKnownCategory` 、またはの呼び出しが `AddUserTasks` この数を超えると、エラーが返されます。

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a> CJumpList:: GetRemovedItems

削除された変換先を表す項目の配列を返します。

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

削除された変換先は、ジャンプリストの初期化中に取得されます。 新しい変換先リストを生成する場合、アプリケーションはまず、削除された変換先リストを処理し、削除されたリスト列挙子によって返される項目の追跡データをクリアします。 アプリケーションが、現在の呼び出しが開始されたトランザクションで削除されたばかりの項目を提供しようとすると `BeginList` 、その項目を再追加したメソッド呼び出しは失敗し、アプリケーションが削除されたリストを尊重するようになります。

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a> CJumpList:: InitializeList

リスト構築トランザクションを開始します。

```
BOOL InitializeList();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

を使用してへのポインターを取得したり、を使用して `ICustomDestinationList` 使用 `GetDestinationList` 可能なスロットの数を取得したり、を使用して削除した `GetMaxSlots` 項目の一覧 `GetRemovedItems` を取得したりする場合を除き、このメソッドを明示的に呼び出す必要はありません

## <a name="cjumplistsetappid"></a><a name="setappid"></a> CJumpList:: SetAppID

ビルドされるリストのアプリケーションユーザーモデル ID を設定します。

```cpp
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>パラメーター

*strAppID*<br/>
アプリケーションユーザーモデル ID を指定する文字列。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
