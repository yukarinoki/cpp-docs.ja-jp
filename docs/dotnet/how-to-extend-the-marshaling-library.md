---
description: '詳細については、「方法: マーシャリングライブラリを拡張する」を参照してください。'
title: '方法: マーシャリング ライブラリを拡張する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
ms.openlocfilehash: 829e05002c23f5a5b59efdb5e65dc5769ca7906a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134967"
---
# <a name="how-to-extend-the-marshaling-library"></a>方法: マーシャリング ライブラリを拡張する

このトピックでは、マーシャリングライブラリを拡張して、データ型間の変換をさらに提供する方法について説明します。 ユーザーは、ライブラリで現在サポートされていないデータ変換のマーシャリングライブラリを拡張できます。

マーシャリングライブラリは、 [Marshal_context クラス](../dotnet/marshal-context-class.md)の有無にかかわらず、次の2つの方法のいずれかで拡張できます。 新しい変換にコンテキストが必要かどうかを判断するには、「 [C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md) 」を参照してください。

どちらの場合も、最初に新しいマーシャリング変換用のファイルを作成します。 これは、標準マーシャリングライブラリファイルの整合性を維持するために行います。 プロジェクトを別のコンピューターまたは別のプログラマに移植する場合は、新しいマーシャリングファイルをプロジェクトの残りの部分と共にコピーする必要があります。 この方法では、プロジェクトを受け取るユーザーは新しい変換を受け取ることが保証されるため、ライブラリファイルを変更する必要はありません。

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>コンテキストを必要としない変換でマーシャリングライブラリを拡張するには

1. 新しいマーシャリング関数を格納するファイルを作成します (例、MyMarshal)。

1. 1つまたは複数のマーシャリングライブラリファイルを含めます。

   - 基本データ型の場合は、をマーシャリングします。

   - windows データ型の場合は marshal_windows。

   - C++ 標準ライブラリのデータ型については、marshal_cppstd。

   - ATL データ型の marshal_atl。

1. これらの手順の最後にあるコードを使用して、変換関数を記述します。 このコードでは、は変換先の型、FROM は変換元の型、は変換する `from` パラメーターです。

1. 変換ロジックに関するコメントをコードに置き換えて、 `from` パラメーターをのオブジェクトに変換し、変換されたオブジェクトを返します。

```
namespace msclr {
   namespace interop {
      template<>
      inline TO marshal_as<TO, FROM> (const FROM& from) {
         // Insert conversion logic here, and return a TO parameter.
      }
   }
}
```

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>コンテキストを必要とする変換を使用してマーシャリングライブラリを拡張するには

1. 新しいマーシャリング関数を格納するファイルを作成します (例、MyMarshal)。

1. 1つまたは複数のマーシャリングライブラリファイルを含めます。

   - 基本データ型の場合は、をマーシャリングします。

   - windows データ型の場合は marshal_windows。

   - C++ 標準ライブラリのデータ型については、marshal_cppstd。

   - ATL データ型の marshal_atl。

1. これらの手順の最後にあるコードを使用して、変換関数を記述します。 このコードでは、は変換先の型、FROM は変換元の型、 `toObject` は結果を格納するポインター、 `fromObject` は変換されるパラメーターですが、このコードではになります。

1. の初期化に関するコメントをコードに置き換えて、を `toPtr` 適切な空の値に初期化します。 たとえば、ポインターである場合は、に設定 `NULL` します。

1. 変換ロジックに関するコメントをコードに置き換えて、 `from` パラメーターをのオブジェクトの型 *に* 変換します。 この変換されたオブジェクトはに格納され `toPtr` ます。

1. 設定に関するコメントをコードに置き換えて、 `toObject` `toObject` 変換されたオブジェクトに設定します。

1. ネイティブリソースのクリーンアップに関するコメントをコードに置き換えて、によって割り当てられたメモリを解放 `toPtr` します。 を使用してメモリを割り当てた場合は、を使用して `toPtr` メモリを解放し **`new`** **`delete`** ます。

```
namespace msclr {
   namespace interop {
      template<>
      ref class context_node<TO, FROM> : public context_node_base
      {
      private:
         TO toPtr;
      public:
         context_node(TO& toObject, FROM fromObject)
         {
            // (Step 4) Initialize toPtr to the appropriate empty value.
            // (Step 5) Insert conversion logic here.
            // (Step 6) Set toObject to the converted parameter.
         }
         ~context_node()
         {
            this->!context_node();
         }
      protected:
         !context_node()
         {
            // (Step 7) Clean up native resources.
         }
      };
   }
}
```

## <a name="example-extend-marshaling-library"></a>例: マーシャリングライブラリの拡張

次の例では、コンテキストを必要としない変換を使用して、マーシャリングライブラリを拡張します。 この例では、コードによって、従業員情報がネイティブデータ型からマネージデータ型に変換されます。

```cpp
// MyMarshalNoContext.cpp
// compile with: /clr
#include <msclr/marshal.h>

value struct ManagedEmp {
   System::String^ name;
   System::String^ address;
   int zipCode;
};

struct NativeEmp {
   char* name;
   char* address;
   int zipCode;
};

namespace msclr {
   namespace interop {
      template<>
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {
         ManagedEmp^ toValue = gcnew ManagedEmp;
         toValue->name = marshal_as<System::String^>(from.name);
         toValue->address = marshal_as<System::String^>(from.address);
         toValue->zipCode = from.zipCode;
         return toValue;
      }
   }
}

using namespace System;
using namespace msclr::interop;

int main() {
   NativeEmp employee;

   employee.name = "Jeff Smith";
   employee.address = "123 Main Street";
   employee.zipCode = 98111;

   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);

   Console::WriteLine("Managed name: {0}", result->name);
   Console::WriteLine("Managed address: {0}", result->address);
   Console::WriteLine("Managed zip code: {0}", result->zipCode);

   return 0;
}
```

前の例では、関数は、変換され `marshal_as` たデータへのハンドルを返します。 これは、データの追加コピーを作成しないようにするために行われました。 変数を直接返すと、それに関連する不要なパフォーマンスコストが発生します。

```Output
Managed name: Jeff Smith
Managed address: 123 Main Street
Managed zip code: 98111
```

## <a name="example-convert-employee-information"></a>例: 従業員情報を変換する

次の例では、従業員情報をマネージデータ型からネイティブデータ型に変換します。 この変換にはマーシャリングコンテキストが必要です。

```cpp
// MyMarshalContext.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr/marshal.h>

value struct ManagedEmp {
   System::String^ name;
   System::String^ address;
   int zipCode;
};

struct NativeEmp {
   const char* name;
   const char* address;
   int zipCode;
};

namespace msclr {
   namespace interop {
      template<>
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base
      {
      private:
         NativeEmp* toPtr;
         marshal_context context;
      public:
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)
         {
            // Conversion logic starts here
            toPtr = NULL;

            const char* nativeName;
            const char* nativeAddress;

            // Convert the name from String^ to const char*.
            System::String^ tempValue = fromObject->name;
            nativeName = context.marshal_as<const char*>(tempValue);

            // Convert the address from String^ to const char*.
            tempValue = fromObject->address;
            nativeAddress = context.marshal_as<const char*>(tempValue);

            toPtr = new NativeEmp();
            toPtr->name = nativeName;
            toPtr->address = nativeAddress;
            toPtr->zipCode = fromObject->zipCode;

            toObject = toPtr;
         }
         ~context_node()
         {
            this->!context_node();
         }
      protected:
         !context_node()
         {
            // When the context is deleted, it will free the memory
            // allocated for toPtr->name and toPtr->address, so toPtr
            // is the only memory that needs to be freed.
            if (toPtr != NULL) {
               delete toPtr;
               toPtr = NULL;
            }
         }
      };
   }
}

using namespace System;
using namespace msclr::interop;

int main() {
   ManagedEmp^ employee = gcnew ManagedEmp();

   employee->name = gcnew String("Jeff Smith");
   employee->address = gcnew String("123 Main Street");
   employee->zipCode = 98111;

   marshal_context context;
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);

   if (result != NULL) {
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",
         result->name, result->address, result->zipCode);
   }

   return 0;
}
```

```Output
Native name: Jeff Smith
Native address: 123 Main Street
Native zip code: 98111
```

## <a name="see-also"></a>関連項目

[C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)
