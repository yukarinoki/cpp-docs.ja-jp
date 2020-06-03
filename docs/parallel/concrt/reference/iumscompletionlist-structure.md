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
ms.openlocfilehash: c388cc98aedbd35b2d0e00a4653a85a47abcb838
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368122"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList 構造体

UMS の完了リストを表します。 UMS スレッドがブロックされると、基になる仮想プロセッサ ルートでスケジュールする内容を決定するためにスケジューラで指定されているスケジュールのコンテキストがディスパッチされ、元のスレッドがブロックされます。 元のスレッドがブロックされない場合、オペレーション システムは、このインターフェイスからアクセスできる完了リストのキューにそれを配置します。 スケジューラは指定されたスケジュール コンテキスト、または作業を検索するその他の場所にある完了リストを照会できます。

## <a name="syntax"></a>構文

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[インプリートリスト::ブロック解除通知](#getunblocknotifications)|このメソッドが最後に`IUMSUnblockNotification`呼び出されてから、関連付けられたスレッド プロキシがブロック解除された実行コンテキストを表すインターフェイスのチェーンを取得します。|

## <a name="remarks"></a>解説

スケジューラは、このインターフェイスを使用して完了リストからアイテムをデキューした後に実行されるアクションに特に注意する必要があります。 項目は、スケジューラーの実行可能コンテキストのリストに配置され、一般にできるだけ早くアクセス可能である必要があります。 キューから取り出された項目の 1 つに任意のロックの所有権が与えられている可能性があります。 スケジューラは、アイテムのデキューの呼び出しと、通常はスケジューラ内からアクセスできるリスト上の項目の配置の間でブロックできる任意の関数呼び出しを行うことはできません。

## <a name="inheritance-hierarchy"></a>継承階層

`IUMSCompletionList`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a>メソッドを終了リスト::ブロック解除通知メソッド

このメソッドが最後に`IUMSUnblockNotification`呼び出されてから、関連付けられたスレッド プロキシがブロック解除された実行コンテキストを表すインターフェイスのチェーンを取得します。

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>戻り値

インターフェイスの`IUMSUnblockNotification`チェーン。

### <a name="remarks"></a>解説

実行コンテキストのスケジュールが変更されると、返される通知は無効になります。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification 構造体](iumsunblocknotification-structure.md)
