---
title: delete 演算子 (C++)
ms.date: 11/04/2016
f1_keywords:
- delete_cpp
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
ms.openlocfilehash: 5e4f5685ea1bb8cd7c405373ba774fe36af08672
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398967"
---
# <a name="delete-operator-c"></a>delete 演算子 (C++)

メモリのブロックを解放します。

## <a name="syntax"></a>構文

```
[::] delete cast-expression
[::] delete [ ] cast-expression
```

## <a name="remarks"></a>Remarks

*キャスト式*引数は以前に作成されたオブジェクトに割り当てられたメモリ ブロックへのポインターである必要があります、 [new 演算子](../cpp/new-operator-cpp.md)します。 **削除**演算子は、型の結果**void**し、そのため、値は返されません。 例えば:

```cpp
CDialog* MyDialog = new CDialog;
// use MyDialog
delete MyDialog;
```

使用して**削除**で割り当てられていないオブジェクトへのポインターで**新しい**予期しない結果が得られます。 ただし、使用することができます、**削除**で値が 0 のポインター。 このプロビジョニングは、ことを意味と**新しい**失敗時、失敗の結果を削除するのには 0 を返します**新しい**操作は問題ありません。 参照してください[新しい演算子と delete 演算子](../cpp/new-and-delete-operators.md)詳細についてはします。

**新しい**と**削除**演算子は、配列を含む、組み込みの型も使用できます。 `pointer` が配列を参照している場合は、`pointer` の前に空のかっこを記述します。

```cpp
int* set = new int[100];
//use set[]
delete [] set;
```

使用して、**削除**演算子をオブジェクトにそのメモリの割り当てを解除します。 オブジェクトを削除した後でポインターを逆参照するプログラムは、予期しない結果になるか、クラッシュする可能性があります。

ときに**削除**は C++ クラス オブジェクトのメモリの割り当てを解除するために使用に (オブジェクトにデストラクターがある場合)、オブジェクトのメモリが割り当て解除される前に、オブジェクトのデストラクターは呼び出されます。

場合、オペランド、**削除**演算子は変更可能な左辺値、オブジェクトが削除された後の値が定義されていません。

## <a name="using-delete"></a>delete の使用

2 つの構文バリアントがある、 [delete 演算子](../cpp/delete-operator-cpp.md): 1 つは 1 つのオブジェクト、他のオブジェクトの配列。 次のコードは、これらがどのように違うかを示します。

```cpp
// expre_Using_delete.cpp
struct UDType
{
};

int main()
{
   // Allocate a user-defined object, UDObject, and an object
   //  of type double on the free store using the
   //  new operator.
   UDType *UDObject = new UDType;
   double *dObject = new double;
   // Delete the two objects.
   delete UDObject;
   delete dObject;
   // Allocate an array of user-defined objects on the
   // free store using the new operator.
   UDType (*UDArr)[7] = new UDType[5][7];
   // Use the array syntax to delete the array of objects.
   delete [] UDArr;
}
```

オブジェクトに対して配列形式の削除 (delete [ ]) を使用した場合、および配列に対して非配列形式の削除を使用した場合は、未定義の結果が生成されます。

## <a name="example"></a>例

使用例について**削除**を参照してください[new 演算子](../cpp/new-operator-cpp.md)します。

## <a name="how-delete-works"></a>delete の動作方法

Delete 演算子関数を呼び出す**delete 演算子**します。

オブジェクトのクラス型ではありません ([クラス](../cpp/class-cpp.md)、[構造体](../cpp/struct-cpp.md)、または[共用体](../cpp/unions.md))、グローバルな delete 演算子が呼び出されます。 クラス型のオブジェクトでは、delete 式の先頭が単項スコープ解決演算子 (::) である場合に、deallocation 関数の名前がグローバル スコープで解決されます。 それ以外の場合、delete 演算子は、メモリ (ポインターが null でない場合) の割り当てを解除する前に、オブジェクトのデストラクターを呼び出します。 delete 演算子は、クラス単位で定義できます。指定のクラスの定義がない場合、グローバル delete 演算子が呼び出されます。 静的な型に仮想デストラクターが含まれるクラス オブジェクトの割り当ての解放に delete 式を使用した場合、deallocation 関数は動的な型のオブジェクトの仮想デストラクターを通じて解決されます。

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[new および delete 演算子](../cpp/new-and-delete-operators.md)