---
title: IUMSCompletionList 構造体
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: 567b8668934d81c49757660d1a60ca74eb033e68
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273916"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList 構造体

UMS の完了リストを表します。 UMS スレッドがブロックされると、基になる仮想プロセッサ ルートでスケジュールする内容を決定するためにスケジューラで指定されているスケジュールのコンテキストがディスパッチされ、元のスレッドがブロックされます。 元のスレッドがブロックされない場合、オペレーション システムは、このインターフェイスからアクセスできる完了リストのキューにそれを配置します。 スケジューラは指定されたスケジュール コンテキスト、または作業を検索するその他の場所にある完了リストを照会できます。

## <a name="syntax"></a>構文

```
struct IUMSCompletionList;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|チェーンを取得します。`IUMSUnblockNotification`プロキシは、最後にこのメソッドにブロック解除が関連付けられているスレッドが呼び出された実行コンテキストを表すインターフェイス。|

## <a name="remarks"></a>Remarks

スケジューラは、入力候補一覧から項目をキューから削除するには、このインターフェイスを使用して後で実行される操作について非常に慎重である必要があります。 項目は、実行可能なコンテキストのスケジューラの一覧に配置する必要があり、できるだけ早く一般にアクセスできるようにします。 デキューされる項目のいずれかを設定した任意のロックの所有権がまったくことができます。 項目をデキューする呼び出しと一般にアクセスできるからスケジューラ内でリストにこれらのアイテムの配置間ブロックできる任意の関数呼び出しは、スケジューラでは、ありません。

## <a name="inheritance-hierarchy"></a>継承階層

`IUMSCompletionList`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="getunblocknotifications"></a>  IUMSCompletionList::GetUnblockNotifications Method

チェーンを取得します。`IUMSUnblockNotification`プロキシは、最後にこのメソッドにブロック解除が関連付けられているスレッドが呼び出された実行コンテキストを表すインターフェイス。

```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>戻り値

チェーン`IUMSUnblockNotification`インターフェイス。

### <a name="remarks"></a>Remarks

実行コンテキストが再スケジュールすると、返される通知が無効です。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification 構造体](iumsunblocknotification-structure.md)
