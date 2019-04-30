---
title: イベント処理
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: 4c6701f04544b336de97196e8b65f4d0cd4be296
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392155"
---
# <a name="event-handling"></a>イベント処理

イベント処理は主に COM クラスのサポートされています (通常は ATL クラスを使用して、COM オブジェクトを実装する C++ クラス、または[コクラス](../windows/coclass.md)属性)。 詳細については、次を参照してください。 [COM でのイベント処理](../cpp/event-handling-in-com.md)します。

イベント処理はネイティブ C++ クラス (COM オブジェクトを実装しない C++ クラス) でサポートされていますが、このサポートは非推奨とされており、将来のリリースでは削除されます。  詳細については、次を参照してください。[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)します。

イベント処理では、シングルスレッドおよびマルチスレッドの使用をサポートし、同時マルチスレッド アクセスからデータを保護できます。 また、サブクラスをイベント ソース クラスまたはイベント レシーバー クラスから派生させ、その派生クラスの拡張イベント ソースと拡張イベント受信をサポートします。

Visual C++ には、イベントとイベント ハンドラーを宣言するための属性とキーワードが含まれています。 イベント属性とキーワードは、CLR プログラムとネイティブ C++ プログラムで使用できます。

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