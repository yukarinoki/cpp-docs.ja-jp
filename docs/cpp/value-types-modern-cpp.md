---
title: 値の型 (Modern C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e49c97bca86b8d2debde2f5b132f7dde16998e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423419"
---
# <a name="value-types-modern-c"></a>値型 (Modern C++)
C++ のクラスは、既定値の型ではします。 このトピックでは、値の型とその使用に関連する問題の概要を説明します。  
  
## <a name="value-vs-reference-types"></a>値の型と参照型  
 既に説明したように、C++ のクラスは、既定値の型ではします。 参照の型は、オブジェクト指向プログラミングをサポートするポリモーフィックな動作を有効にする、それらを指定することができます。 値の型は参照型が基本クラスと仮想関数はポリモーフィックな目的ではメモリとレイアウトのコントロールの観点から表示場合があります。 既定では、値型はコピー可能なつまりでは常にコピー コンス トラクターとコピー代入演算子です。 参照型のクラスを変更不可能 (コピー コンス トラクターとコピー代入演算子を無効にする) およびその対象ポリモーフィズムをサポートする仮想デストラクターを使用します。 値の型は、コピーされるときに常に提供する 2 つの独立した値とは別に変更できる内容についてもです。 参照型では、id、オブジェクトの種類は、それに関するですか。 このため、「参照の種類」「ポリモーフィックな型」とも呼びます。  
  
 実際にする場合、参照のような型 (基本クラス、仮想関数)、無効にする必要明示的にコピーするには、ように、`MyRefType`次のコード内のクラスです。  
  
```cpp  
// cl /EHsc /nologo /W4  
  
class MyRefType {  
private:  
    MyRefType & operator=(const MyRefType &);  
    MyRefType(const MyRefType &);  
public:  
    MyRefType () {}  
};  
  
int main()  
{  
    MyRefType Data1, Data2;  
    // ...  
    Data1 = Data2;  
}  
```  
  
 上記のコードをコンパイルすると、次のエラーが発生します。  
  
```Output  
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'  
        meow.cpp(5) : see declaration of 'MyRefType::operator ='  
        meow.cpp(3) : see declaration of 'MyRefType'  
  
```  
  
## <a name="value-types-and-move-efficiency"></a>値型と効率性を移動  
 新しいコピーの最適化のため、割り当てのコピーのオーバーヘッドが回避されます。 たとえば、文字列のベクターの途中で文字列を挿入するときにするにはありませんコピー再割り当てオーバーヘッドだけ、移動、でも自体のベクターの拡大になります。 これは、インスタンスの 2 つの非常に大きなオブジェクトの追加操作を実行するその他の操作にも適用されます。 これらの値の操作の最適化を有効する方法 一部の C++ コンパイラでコンパイラが有効になりますこのを暗黙的に、コピー コンス トラクターは、コンパイラによって自動的に生成できるのと同様にします。 ただし、Visual c では、クラスは「オプトイン」に、クラス定義で宣言することによって割り当てとコンス トラクターを移動する必要があります。 二重のアンパサンドを使用してこれを実現 ((& a) (& a))、適切なメンバーに右辺値参照関数の宣言と定義の移動コンス トラクターと移動代入方法です。  また、正しいコードをソース オブジェクトから「内容を盗み出そう」を挿入する必要があります。  
  
 どのようにして有効になっているを移動する必要があるかどうかですか。 場合は既に有効になっている構造をコピーする必要がある、多くの場合の詳細コピーよりも安価であることができる場合に有効な移動します。 ただし、サポートを移動する必要がある場合は、こと必ずしも意味コピーを有効になっています。 この後者の場合に、"移動のみ type"が呼び出されます。 たとえば、標準ライブラリでは既には`unique_ptr`します。 古い`auto_ptr`があり、廃止予定に置き換えられました`unique_ptr`C の以前のバージョンでの移動セマンティクスのサポートの不足により正確にします。  
  
 移動セマンティクスを使用して値渡しの戻り値または中央部での挿入することができます。 移動は、コピーの最適化です。 回避策としてヒープ割り当ての必要性があります。 次の疑似コードについて考えてみます。  
  
```cpp  
#include <set>  
#include <vector>  
#include <string>  
using namespace std;  
  
//...  
set<widget> LoadHugeData() {  
    set<widget> ret;  
    // ... load data from disk and populate ret  
    return ret;  
}  
//...  
widgets = LoadHugeData();   // efficient, no deep copy  
  
vector<string> v = IfIHadAMillionStrings();  
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle  
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)  
//...  
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );  
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);  
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );  
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);  
//...  
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies  
```  
  
### <a name="enabling-move-for-appropriate-value-types"></a>適切な値の型の移動を有効にします。  
 移動をディープ コピーよりも安価できる値のようなクラス、移動の構築を有効にし、効率を上げるのための割り当てに移動します。 次の疑似コードについて考えてみます。  
  
```cpp  
#include <memory>  
#include <stdexcept>  
using namespace std;  
// ...  
class my_class {  
    unique_ptr<BigHugeData> data;  
public:  
    my_class( my_class&& other )   // move construction  
        : data( move( other.data ) ) { }  
    my_class& operator=( my_class&& other )   // move assignment  
    { data = move( other.data ); return *this; }  
    // ...  
    void method() {   // check (if appropriate)  
        if( !data )   
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");  
    }  
};  
  
```  
  
 コピーの構築/割り当てを有効にした場合、詳細コピーより低コストであることができる場合も移動の構築/割り当てを有効にします。  
  
 いくつか*非値*の種類は移動のみなどと、リソースの所有権を転送のみを複製することはできません。 例 : `unique_ptr`。  
  
## <a name="section"></a>セクション  
 Content  
  
## <a name="see-also"></a>関連項目  
 [C++ 型システム](../cpp/cpp-type-system-modern-cpp.md)   
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)