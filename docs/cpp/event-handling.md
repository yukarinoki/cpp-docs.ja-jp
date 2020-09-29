---
title: イベント処理
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: 4ed2dd2140176fe302d2b6800a3aa7768d17eedd
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498899"
---
# <a name="event-handling"></a>イベント処理

イベント処理は、主に COM クラス (COM オブジェクトを実装する C++ クラス (通常は ATL クラスまたは [coclass](../windows/attributes/coclass.md) 属性を使用)) でサポートされています。 詳細については、「 [COM でのイベント処理](../cpp/event-handling-in-com.md)」を参照してください。

イベント処理はネイティブ C++ クラス (COM オブジェクトを実装しない C++ クラス) でサポートされていますが、このサポートは非推奨とされており、将来のリリースでは削除されます。  詳細については、「 [ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)」を参照してください。

イベント処理では、シングルスレッドおよびマルチスレッドの使用をサポートし、同時マルチスレッド アクセスからデータを保護できます。 また、サブクラスをイベント ソース クラスまたはイベント レシーバー クラスから派生させ、その派生クラスの拡張イベント ソースと拡張イベント受信をサポートします。

Microsoft C++ コンパイラには、イベントとイベントハンドラーを宣言するための属性とキーワードが含まれています。 イベント属性とキーワードは、CLR プログラムとネイティブ C++ プログラムで使用できます。

|トピック|説明|
|-----------|-----------------|
|[event_source](../windows/attributes/event-source.md)|イベント ソースを作成します。|
|[event_receiver](../windows/attributes/event-receiver.md)|イベント レシーバー (シンク) を作成します。|
|[__event](../cpp/event.md)|イベントを宣言します。|
|[__raise](../cpp/raise.md)|イベントの呼び出しサイトを強調します。|
|[__hook](../cpp/hook.md)|ハンドラー メソッドをイベントに関連付けます。|
|[__unhook](../cpp/unhook.md)|イベントからハンドラー メソッドの関連付けを解除します。|

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
