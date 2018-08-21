---
title: イベント処理 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91fded4380875515da81b87c5ffd74665df01b21
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408028"
---
# <a name="event-handling"></a>イベント処理
イベント処理は主に COM クラスのサポートされています (通常は ATL クラスを使用して、COM オブジェクトを実装する C++ クラス、または[コクラス](../windows/coclass.md)属性)。  詳細については、次を参照してください。 [COM でのイベント処理](../cpp/event-handling-in-com.md)します。  
  
 イベント処理はネイティブ C++ クラス (COM オブジェクトを実装しない C++ クラス) でサポートされていますが、このサポートは非推奨とされており、将来のリリースでは削除されます。  詳細については、次を参照してください。[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)します。  
  
 イベント処理では、シングルスレッドおよびマルチスレッドの使用をサポートし、同時マルチスレッド アクセスからデータを保護できます。 また、サブクラスをイベント ソース クラスまたはイベント レシーバー クラスから派生させ、その派生クラスの拡張イベント ソースと拡張イベント受信をサポートします。  
  
 Visual C++ には、イベントとイベント ハンドラーを宣言するための属性とキーワードが含まれています。 イベント属性とキーワードは、CLR プログラムとネイティブ C++ プログラムで使用できます。  
  
|トピック|説明|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|イベント ソースを作成します。|  
|[event_receiver](../windows/event-receiver.md)|イベント レシーバー (シンク) を作成します。|  
|[__event](../cpp/event.md)|イベントを宣言します。|  
|[__raise](../cpp/raise.md)|イベントの呼び出しサイトを強調します。|  
|[__hook](../cpp/hook.md)|ハンドラー メソッドをイベントに関連付けます。|  
|[__unhook](../cpp/unhook.md)|イベントからハンドラー メソッドの関連付けを解除します。|  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [キーワード](../cpp/keywords-cpp.md)   