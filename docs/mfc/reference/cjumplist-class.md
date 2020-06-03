---
title: クラスをジャンプします。
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
ms.openlocfilehash: 2e45e2e58bd51d36b6412940b7ed01aa119017ed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754938"
---
# <a name="cjumplist-class"></a>クラスをジャンプします。

A`CJumpList`は、タスク バーのアイコンを右クリックしたときに表示されるショートカットのリストです。

## <a name="syntax"></a>構文

```
class CJumpList;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ジャンプリスト::Cジャンプリスト](#cjumplist)|`CJumpList` オブジェクトを構築します。|
|[ジャンプリスト::~Cジャンプリスト](#_dtorcjumplist)|`CJumpList` オブジェクトを破棄します。|

|名前|説明|
|----------|-----------------|
|[ジャンプリスト::アボートリスト](#abortlist)|コミットせずにリスト作成トランザクションを中止します。|
|[ジャンプリスト::デスティネーションの追加](#adddestination)|オーバーロードされます。 リストに宛先を追加します。|
|[ジャンプリスト::アドオン既知のカテゴリ](#addknowncategory)|リストに既知のカテゴリを追加します。|
|[ジャンプリスト::タスクの追加](#addtask)|オーバーロードされます。 正規のタスクカテゴリに項目を追加します。|
|[タスクの追加](#addtasks)|正規のタスクカテゴリに項目を追加します。|
|[次の項目を使用します。](#addtaskseparator)|タスク間に区切り記号を追加します。|
|[ジャンプリスト::クリアオール](#clearall)|現在のインスタンスに追加されたすべてのタスクと宛先を`CJumpList`削除します。|
|[ジャンプリスト::クリアオールデスティネーション](#clearalldestinations)|`CJumpList`現在のインスタンスに追加されたすべての宛先を削除します。|
|[クジャンプリスト::コミットリスト](#commitlist)|リスト作成トランザクションを終了し、報告されたリストを関連ストア (この場合はレジストリ) にコミットします。|
|[ジャンプリスト::取得デスティネーションリスト](#getdestinationlist)|宛先リストへのインターフェイス ポインターを取得します。|
|[ジャンプリスト::ゲットマックススロット](#getmaxslots)|呼び出し元アプリケーションの宛先メニューに表示できるカテゴリ ヘッダーを含む、項目の最大数を取得します。|
|[次の項目を削除します。](#getremoveditems)|削除された宛先を表す項目の配列を返します。|
|[リストを初期化します。](#initializelist)|リスト作成トランザクションを開始します。|
|[ジャンプリスト::セットアプID](#setappid)|ビルドするリストのアプリケーション ユーザー モデル ID を設定します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxadv.h

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a>ジャンプリスト::~Cジャンプリスト

`CJumpList` オブジェクトを破棄します。

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a>ジャンプリスト::アボートリスト

コミットせずにリスト作成トランザクションを中止します。

```cpp
void AbortList();
```

### <a name="remarks"></a>解説

このメソッドを呼び出すことは、 を`CJumpList`呼び`CommitList`出さずに破棄するのと同じ効果があります。

## <a name="cjumplistadddestination"></a><a name="adddestination"></a>ジャンプリスト::デスティネーションの追加

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

*カテゴリ名*<br/>
カテゴリ名を指定します。 指定したカテゴリが存在しない場合は、作成されます。

*エストディネーションパス*<br/>
コピー先ファイルへのパスを指定します。

*スズ*<br/>
カテゴリ名を指定します。 指定したカテゴリが存在しない場合は、作成されます。

*をクリックします。*<br/>
追加する宛先を表すシェル項目を指定します。

*をクリックします。*<br/>
追加する宛先を表すシェル リンクを指定します。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

内部の`CJumpList`インスタンスは、追加された宛先を蓄積し、それらを に`CommitList`コミットします。

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a>ジャンプリスト::アドオン既知のカテゴリ

リストに既知のカテゴリを追加します。

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>パラメーター

*category*<br/>
既知のカテゴリの種類を指定します。 KDC_RECENTまたはKDC_KNOWN。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

既知のカテゴリは、使用するすべてのアプリケーションに対して自動的に計算される [頻繁`SHAddToRecentDocs`] カテゴリと [最近] カテゴリです (または、シェルがアプリケーションの代わりに呼び出す場合に間接的に使用する場合)。

## <a name="cjumplistaddtask"></a><a name="addtask"></a>ジャンプリスト::タスクの追加

正規のタスクカテゴリに項目を追加します。

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

*実行パス*<br/>
ターゲット タスクのパスを指定します。

*コマンドライン引数*<br/>
によって指定された実行可能ファイルのコマンド ライン引数*を指定します*。

*strタイトル*<br/>
宛先リストに表示されるタスク名。

*スズイコンロケーション*<br/>
[宛先リスト] にタイトルと共に表示されるアイコンの場所。

*アイコンインデックス*<br/>
アイコンインデックス。

*をクリックします。*<br/>
追加するタスクを表すシェル リンク。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

のインスタンスは`CJumpList`、指定されたタスクを累積し、それらを宛先リストに`CommitList`追加します。 タスク項目は、アプリケーションのコピー先メニューの下部にあるカテゴリに表示されます。 このカテゴリは、UI に入力される他のすべてのカテゴリよりも優先されます。

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a>タスクの追加

正規のタスクカテゴリに項目を追加します。

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>パラメーター

*コレクション*<br/>
追加するタスクのコレクション。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

CJumpList のインスタンスは、指定されたタスクを蓄積し、それらを宛先リスト`CommitList`に追加します。 タスク項目は、アプリケーションのコピー先メニューの下部にあるカテゴリに表示されます。 このカテゴリは、UI に入力される他のすべてのカテゴリよりも優先されます。

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a>次の項目を使用します。

タスク間に区切り記号を追加します。

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外、成功しなかった場合は 0 以外の値を返します。

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a>ジャンプリスト::Cジャンプリスト

`CJumpList` オブジェクトを構築します。

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>パラメーター

*bオートコミット*<br/>
このパラメーターが FALSE の場合、リストはデストラクターで自動的にコミットされません。

## <a name="cjumplistclearall"></a><a name="clearall"></a>ジャンプリスト::クリアオール

現在のインスタンスに追加されたすべてのタスクと宛先を`CJumpList`削除します。

```cpp
void ClearAll();
```

### <a name="remarks"></a>解説

このメソッドは、すべてのデータおよび内部インターフェイスをクリアし、解放します。

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a>ジャンプリスト::クリアオールデスティネーション

これまでに CJumpList の現在のインスタンスに追加されたすべての宛先を削除します。

```cpp
void ClearAllDestinations();
```

### <a name="remarks"></a>解説

宛先リストの現在のセッションでこれまでに追加されたすべての宛先を削除し、他の宛先を再度追加する必要がある場合は、この関数を呼び出します。 内部`ICustomDestinationList`が初期化されている場合、それは生き残っています。

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a>クジャンプリスト::コミットリスト

リスト作成トランザクションを終了し、報告されたリストを関連ストア (この場合はレジストリ) にコミットします。

```
BOOL CommitList();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

コミットはアトミックです。 コミットが失敗した場合は、エラーが返されます。  呼`CommitList`び出されると、削除された項目の現在のリストがクリーンアップされます。 このメソッドを呼び出すと、アクティブなリスト作成トランザクションが存在しないようにオブジェクトがリセットされます。 リストを更新するには、`BeginList`再度呼び出す必要があります。

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a>ジャンプリスト::取得デスティネーションリスト

宛先リストへのインターフェイス ポインターを取得します。

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

ジャンプ リストが初期化されていない場合、またはコミットまたは中止された場合、返される値は NULL になります。

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a>ジャンプリスト::ゲットマックススロット

呼び出し元アプリケーションの宛先メニューに表示できるカテゴリ ヘッダーを含む、項目の最大数を取得します。

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

アプリケーションは、この値まで組み合わせた多数のアイテムとカテゴリ ヘッダーのみを報告できます。 を`AppendKnownCategory`呼び`AppendCategory`出すか、`AddUserTasks`この数を超えると、失敗が返されます。

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a>次の項目を削除します。

削除された宛先を表す項目の配列を返します。

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

削除された宛先は、ジャンプ リストの初期化中に取得されます。 新しい宛先リストを生成する場合、アプリケーションは最初に削除された宛先リストを処理し、削除されたリスト列挙子によって返される項目の追跡データをクリアすることが想定されます。 アプリケーションが、現在の呼び出しが開始したトランザクションで削除された項目を`BeginList`提供しようとすると、その項目を再度追加したメソッド呼び出しは失敗し、アプリケーションが削除されたリストを確実に尊重します。

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a>リストを初期化します。

リスト作成トランザクションを開始します。

```
BOOL InitializeList();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

を使用して、使用するスロットの数、または`ICustomDestinationList`を使用`GetDestinationList``GetMaxSlots`して削除された項目のリストを使用するポインタを取得する場合を除き、このメソッドを`GetRemovedItems`明示的に呼び出す必要はありません。

## <a name="cjumplistsetappid"></a><a name="setappid"></a>ジャンプリスト::セットアプID

ビルドするリストのアプリケーション ユーザー モデル ID を設定します。

```cpp
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
アプリケーション ユーザー モデル ID を指定する文字列。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
