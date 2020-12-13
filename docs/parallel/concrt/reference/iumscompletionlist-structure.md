---
description: 詳細については、「Iums補完リストの構造」を参照してください。
title: IUMSCompletionList 構造体
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: b54766e8b1c6f2e7c0afbb5e4e9a8efc0c455b4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334347"
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
|[IumsGetUnblockNotifications List::](#getunblocknotifications)|`IUMSUnblockNotification`このメソッドが最後に呼び出された後に、関連付けられたスレッドプロキシによってブロック解除された実行コンテキストを表すインターフェイスのチェーンを取得します。|

## <a name="remarks"></a>解説

スケジューラは、このインターフェイスを利用して入力候補一覧から項目をデキューした後に実行されるアクションについて、非常に注意する必要があります。 項目はスケジューラの実行可能なコンテキストの一覧に配置され、一般にできるだけ早くアクセスできる必要があります。 デキューされた項目の1つに、任意のロックの所有権が与えられている可能性があります。 スケジューラは、デキュー項目への呼び出しと、スケジューラ内から一般にアクセスできるリスト上の項目の配置との間でブロックされる可能性がある任意の関数呼び出しを行うことができません。

## <a name="inheritance-hierarchy"></a>継承階層

`IUMSCompletionList`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a> IumsGetUnblockNotifications List:: メソッド

`IUMSUnblockNotification`このメソッドが最後に呼び出された後に、関連付けられたスレッドプロキシによってブロック解除された実行コンテキストを表すインターフェイスのチェーンを取得します。

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>戻り値

インターフェイスのチェーン `IUMSUnblockNotification` 。

### <a name="remarks"></a>解説

実行コンテキストが再スケジュールされると、返された通知は無効になります。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification 構造体](iumsunblocknotification-structure.md)
