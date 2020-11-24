---
title: イベント処理
description: Microsoft C++ 拡張機能が COM とネイティブの両方のイベント処理をサポートするしくみについて説明します。
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: de8cd6dfac2b83e850ec62ff88e192d1c60e427e
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483130"
---
# <a name="event-handling"></a>イベント処理

イベント処理は、主に COM クラス (COM オブジェクトを実装する C++ クラス (通常は ATL クラスまたは [coclass](../windows/attributes/coclass.md) 属性を使用)) でサポートされています。 詳細については、「 [COM でのイベント処理](../cpp/event-handling-in-com.md)」を参照してください。

イベント処理は、ネイティブ C++ クラス (COM オブジェクトを実装しない C++ クラス) でもサポートされています。 ネイティブ C++ のイベント処理サポートは非推奨とされ、今後のリリースでは削除される予定です。 詳細については、「 [ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)」を参照してください。

> [!NOTE]
> ネイティブ C++ のイベント属性は、標準 C++ と互換性がありません。 準拠モードを指定するとコンパイルされません [`/permissive-`](../build/reference/permissive-standards-conformance.md) 。

イベント処理では、単一およびマルチスレッドの両方の使用がサポートされます。 同時マルチスレッドアクセスからデータを保護します。 イベントソースまたはレシーバークラスからサブクラスを派生させることができます。 これらのサブクラスでは、拡張イベントソーシングと受信がサポートされます。

Microsoft C++ コンパイラには、イベントとイベントハンドラーを宣言するための属性とキーワードが含まれています。 イベント属性とキーワードは、CLR プログラムとネイティブ C++ プログラムで使用できます。

| [アーティクル] | 説明 |
|--|--|
| [`event_source`](../windows/attributes/event-source.md) | イベント ソースを作成します。 |
| [`event_receiver`](../windows/attributes/event-receiver.md) | イベント レシーバー (シンク) を作成します。 |
| [`__event`](../cpp/event.md) | イベントを宣言します。 |
| [`__raise`](../cpp/raise.md) | イベントの呼び出しサイトを強調します。 |
| [`__hook`](../cpp/hook.md) | ハンドラー メソッドをイベントに関連付けます。 |
| [`__unhook`](../cpp/unhook.md) | イベントからハンドラーメソッドの関連付けを解除します。 |

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)\
[キーワード](../cpp/keywords-cpp.md)
