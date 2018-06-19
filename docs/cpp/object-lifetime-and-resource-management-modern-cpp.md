---
title: オブジェクトの有効期間とリソースの管理 (Modern C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 634bef1bf9d2d3128497a1321631ca8665fed144
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423497"
---
# <a name="object-lifetime-and-resource-management-modern-c"></a>オブジェクトの有効期間とリソースの管理 (Modern C++)
管理対象の言語とは異なり、C++ はプログラムを実行すると自動的にいいえで長く-使用メモリ リソースを解放するガベージ コレクション (GC) がありません。 C++ では、リソース管理は、オブジェクトの有効期間に直接関連付けします。 このドキュメントでは、C++ では、オブジェクトの有効期間およびそれを管理する方法に影響する要因について説明します。  
  
 C++ はメモリ以外のリソースを処理しないため、主に、GC にはありません。 のみのような C++ では決定論的デストラクターはメモリと非メモリ リソースを均等に処理できます。 また、GC には、メモリと CPU 消費量、および局所性の高いオーバーヘッドのようなその他の問題があります。 一般性は基本的な問題を巧妙な最適化によって軽減することはできません。  
  
## <a name="concepts"></a>概念  
 オブジェクトの有効期間の管理での重要な点は、カプセル化: オブジェクトのリソースを所有する、または、それらを削除する方法またはでもかどうか、所有するすべてのリソースを一切把握する必要はありませんオブジェクトを使用してだれでもはします。 のみ、オブジェクトを破棄する必要があります。 C++ 言語のコアの目的のオブジェクトが、正しい時刻には、破棄されることを確認するブロックが終了したら、逆の順序で構築します。 オブジェクトが破棄されると、その基底クラスとメンバーが特定の順序で破棄されます。  言語では、ヒープ割り当てやで placement new のような特別な処理を行う場合を除き、オブジェクトを自動的に破棄します。  たとえば、[スマート ポインター](../cpp/smart-pointers-modern-cpp.md)など`unique_ptr`と`shared_ptr`などの C++ 標準ライブラリのコンテナーおよび`vector`、カプセル化`new` / `delete`と`new[]` /`delete[]`デストラクターで、オブジェクトであります。 理由がスマート ポインターや C++ 標準ライブラリのコンテナーを使用するために重要です。  
  
 有効期間の管理にもう 1 つの重要な概念: デストラクターです。 デストラクターは、リリースのリソースをカプセル化します。  (一般的に使用されるニーモニックとは、RRID、リソースのリリースは破棄です)。リソースが"system"から取得し、後で戻す与えることが必要です。  メモリは、最も一般的なリソースがある場合もファイル、ソケット、テクスチャ、およびその他の非メモリ リソース。 リソースの「所有」する必要があることができる場合にも関連付けが完了したら、それを解放するに使用することを意味します。  オブジェクトが破棄されると、そのデストラクターは、所有されているリソースを解放します。  
  
 最終的な概念は、DAG (有向非循環グラフ) です。  プログラムでは所有権の構造は、DAG を形成します。 オブジェクトを所有できるありません自体 — ことはなくのみ不可能なも本質的に意味がなくなります。 2 つのオブジェクトは、3 番目のオブジェクトの所有権を共有できます。  いくつかの種類のリンクが次のように DAG 可能: A が B のメンバー (B は、A を所有する、) C ストア、 `vector<D>` (C は、D の各要素を所有する、) E ストア、 `shared_ptr<F>` (E、F の所有権可能性がありますと共有、他のオブジェクト) などです。  循環がないと、DAG のすべてのリンクは、オブジェクトによって表される限りではなく生のポインター、ハンドル、または他の機構)、デストラクターを持つし、リソースのリークは、言語が原因であるために、不可能なします。 必要なくなった、ガベージ コレクターが実行されているせず後すぐに、リソースは解放されます。 追跡の有効期間はオーバーヘッドがフリーでスタック スコープ、ベース、メンバー、および関連する場合は、の安価な`shared_ptr`します。  
  
### <a name="heap-based-lifetime"></a>ヒープに基づく有効期間  
 ヒープ オブジェクトの有効期間を使用して[スマート ポインター](../cpp/smart-pointers-modern-cpp.md)です。 使用して`shared_ptr`と`make_shared`として、既定のポインターとアロケーター。 使用して`weak_ptr`サイクルを中断、キャッシュ、およびに影響するか、有効期間について何もないオブジェクトを確認します。  
  
```cpp  
void func() {  
  
auto p = make_shared<widget>(); // no leak, and exception safe  
...  
p->draw();   
  
} // no delete required, out-of-scope triggers smart pointer destructor  
  
```  
  
 使用して`unique_ptr`の一意の所有権などで、 *pimpl*表現形式です。 (を参照してください[のコンパイル時のカプセル化の Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md))。ように、`unique_ptr`明示的なすべての主要なターゲット`new`式。  
  
```cpp  
unique_ptr<widget> p(new widget());  
```  
  
 非所有権と観察の生のポインターを使用できます。 所有している以外のポインターが使われます、がリークすることはできません。  
  
```cpp  
class node {  
  ...  
  vector<unique_ptr<node>> children; // node owns children  
  node* parent; // node observes parent, which is not a concern  
  ...  
};  
node::node() : parent(...) { children.emplace_back(new node(...) ); }  
  
```  
  
 パフォーマンスの最適化が必要な場合は、使用する必要があります*整形カプセル化された*ポインター、および削除を明示的に呼び出しを所有しています。 例は、独自の下位レベルのデータ構造を実装する場合です。  
  
### <a name="stack-based-lifetime"></a>スタック ベースの有効期間  
 最新の c++*スタック ベースのスコープ*自動が組み合わされているために、堅牢なコードを記述する強力な手段は、*スタックの有効期間*と*データ メンバーの有効期間*高い効率で。追跡の有効期間は本質的にはオーバーヘッドです。 ヒープ オブジェクトの有効期間は、望ましくない手動による管理を必要とし、生のポインターを使用している場合は特に、リソース リークが発生し、効率のソースを指定できます。 このコードは、スタック ベースのスコープを示しますを考慮してください。  
  
```cpp  
class widget {  
private:  
    gadget g;   // lifetime automatically tied to enclosing object  
public:  
    void draw();  
};  
  
void functionUsingWidget () {  
    widget w;   // lifetime automatically tied to enclosing scope  
                // constructs w, including the w.g gadget member  
    // ...
    w.draw();  
    // ...
} // automatic destruction and deallocation for w and w.g  
  // automatic exception safety,   
  // as if "finally { w.dispose(); w.g.dispose(); }"  
```  
  
 静的な有効期間を多用しない (グローバル静的、関数のローカルの静的) の問題が発生する可能性があるためです。 グローバル オブジェクトのコンス トラクターが例外をスローしたときの動作 通常、アプリはエラー デバッグが困難になることができるようにします。 コンストラクションの順序で静的な有効期間のオブジェクト、問題が発生し、同時実行セーフではありません。 オブジェクトの構築は、問題だけでなく、ポリモーフィズムが必要な場合に特にに、破棄の順序が、複雑になることができます。 でも、オブジェクトまたは変数がない場合ポリモーフィックな複雑な構築/破棄の順序はありません、スレッド セーフである同時実行の問題がまだあります。 マルチ スレッド アプリは、スレッド ローカル ストレージ、リソースのロック、およびその他の特別な対策をしなくても静的オブジェクト内のデータを安全に変更できません。  
  
## <a name="see-also"></a>関連項目  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)