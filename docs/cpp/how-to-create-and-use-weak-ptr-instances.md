---
title: '方法: weak_ptr インスタンスを作成して |Microsoft ドキュメント'
ms.custom: how-to
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8fbbf9d3b427c2451fafe0fae93a531dfd45ad8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415146"
---
# <a name="how-to-create-and-use-weakptr-instances"></a>方法: weak_ptr インスタンスを作成して使用する
オブジェクトには、参照カウントをインクリメントせずに `shared_ptr` の基になるオブジェクトにアクセスする方法を格納する必要が生じることがあります。 通常、この状況は `shared_ptr` インスタンス間に循環参照がある場合に発生します。  
  
 最適なデザインとして、可能な場合は必ずポインターの共有所有権を避けてください。 ただし、`shared_ptr` インスタンスの共有所有権が必要な場合、それらのインスタンス間の循環参照が発生しないようにします。 循環参照を回避できない場合や、何らかの場合で循環参照が必要とされる場合でも、`weak_ptr` を使用して 1 人以上の所有者に別の `shared_ptr` への弱い参照を与えてください。 `weak_ptr` を使用すると、関連するインスタンスの既存のセットに結合される `shared_ptr` を作成できますが、基になるメモリ リソースがまだ有効な場合のみです。 `weak_ptr` 自体は、参照カウントに参加しないため、参照カウントが 0 になるのを防止することはできません。 ただし、`weak_ptr` を使用して、初期化に使用された `shared_ptr` の新しいコピーの取得を試みることはできます。 メモリが既に削除された場合、 **bad_weak_ptr**例外がスローされます。 メモリがまだ有効である場合は、新しい共有ポインターが参照カウントをインクリメントし、`shared_ptr` の変数がスコープ内に入っている限りメモリが有効であることを保証します。  
  
## <a name="example"></a>例  
 次のコード例は、`weak_ptr` を使用して循環依存関係を持つオブジェクトの削除を確証するケースを示しています。 例を調べる際は、代替ソリューションについて検討した後のみ作成されたと見なしてください。 `Controller` オブジェクトは、コンピューター プロセスのいくつかの側面を表しており、独立して動作します。 各コントローラーは、他のコントローラーのステータスのクエリをいつでも実行できる必要があるため、この目的でそれぞれのコントローラーにプライベート `vector<weak_ptr<Controller>>` が含まれています。 各ベクターには循環参照が含まれているため、`weak_ptr` の代わりに `shared_ptr` インスタンスが使用されます。  
  
 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  
  
```Output  
Creating Controller0Creating Controller1Creating Controller2Creating Controller3Creating Controller4push_back to v[0]: 1push_back to v[0]: 2push_back to v[0]: 3push_back to v[0]: 4push_back to v[1]: 0push_back to v[1]: 2push_back to v[1]: 3push_back to v[1]: 4push_back to v[2]: 0push_back to v[2]: 1push_back to v[2]: 3push_back to v[2]: 4push_back to v[3]: 0push_back to v[3]: 1push_back to v[3]: 2push_back to v[3]: 4push_back to v[4]: 0push_back to v[4]: 1push_back to v[4]: 2push_back to v[4]: 3use_count = 1Status of 1 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 2 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 3 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 4 = Onuse_count = 1Status of 0 = OnStatus of 1 = OnStatus of 2 = OnStatus of 3 = OnDestroying Controller0Destroying Controller1Destroying Controller2Destroying Controller3Destroying Controller4Press any key  
```  
  
 テストとして、ベクター `others` を `vector<shared_ptr<Controller>>` に変更した後、出力で、`TestRun` が返されたときにデストラクターが呼び出されないことを確認してください。  
  
## <a name="see-also"></a>関連項目  
 [スマート ポインター](../cpp/smart-pointers-modern-cpp.md)