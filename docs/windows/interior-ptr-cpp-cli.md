---
title: interior_ptr (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d47539c9d7d8e51a061aba35e6b2f3b8f7049951
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328052"
---
# <a name="interiorptr-ccli"></a>interior_ptr (C++/CLI)

*内部ポインター*参照型の内部では、オブジェクト自体へのポインターを宣言します。 内部ポインターには、参照ハンドル、値の型、ボックス化された型のハンドル、マネージ型のメンバーまたはマネージ配列の要素をポイントできます。

## <a name="all-runtimes"></a>すべてのランタイム

(この言語機能にはランタイムに適用される特記事項がありません。)

## <a name="windows-runtime"></a>Windows ランタイム

(この言語機能には Windows ランタイムのみに適用される特記事項がありません。)

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

次の構文例では、内部ポインターを示します。

### <a name="syntax"></a>構文

```cpp
cli::interior_ptr<cv_qualifier type> var = &initializer;
```

### <a name="parameters"></a>パラメーター

*cv_qualifier*<br/>
**const**または**揮発性**修飾子。

*type*<br/>
型*初期化子*します。

*var*<br/>
名前、 **interior_ptr**変数。

*initializer*<br/>
参照型、マネージ配列の場合、またはネイティブ ポインターに割り当てることができるその他のオブジェクトの要素のメンバー。

### <a name="remarks"></a>Remarks

ネイティブ ポインターがオブジェクトのインスタンスを移動、ガベージ コレクターからの結果、マネージ ヒープ上の場所の変更として項目を追跡するためにできません。 インスタンスを正しく参照へのポインター、ランタイムが新しく位置指定のオブジェクトへのポインターを更新する必要があります。

**Interior_ptr**ネイティブ ポインターの機能のスーパー セットを表します。  そのため、何もネイティブ ポインターに割り当てることができますに割り当てることも、 **interior_ptr**します。  比較、ポインターの算術演算などのネイティブ ポインターとして同じ一連の操作を実行する内部ポインターが許可されます。

内部ポインターはスタックでのみ宣言できます。  クラスのメンバーとして、内部ポインターを宣言することはできません。

内部ポインターがスタックにのみ存在するためのアンマネージ ポインターを生成内部ポインターのアドレスを取得します。

**interior_ptr**への暗黙的な変換が**bool**、条件付きステートメントでの使用のことができます。

ガベージ コレクション ヒープ上に移動できないオブジェクトを指す内部ポインターを宣言する方法については、次を参照してください。 [pin_ptr](../windows/pin-ptr-cpp-cli.md)します。

**interior_ptr** cli 名前空間にあります。  参照してください[プラットフォーム、既定では、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)詳細についてはします。

内部ポインターの詳細については、次を参照してください。

- [方法: 内部ポインターおよびマネージド配列を宣言および使用する (C++/CLI)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)

- [方法: interior_ptr キーワードを含む値型を宣言する (C++/CLI)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)

- [方法: 内部ポインターとネイティブ ポインターを使用して関数をオーバーロードする (C++/CLI)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)

- [方法: const キーワードを含む内部ポインターを宣言する (C++/CLI)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次の例では、宣言および参照型を内部ポインターを使用する方法を示します。

```cpp
// interior_ptr.cpp
// compile with: /clr
using namespace System;

ref class MyClass {
public:
   int data;
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   h_MyClass->data = 1;
   Console::WriteLine(h_MyClass->data);

   interior_ptr<int> p = &(h_MyClass->data);
   *p = 2;
   Console::WriteLine(h_MyClass->data);

   // alternatively
   interior_ptr<MyClass ^> p2 = &h_MyClass;
   (*p2)->data = 3;
   Console::WriteLine((*p2)->data);
}
```

```Output
1
2
3
```

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)