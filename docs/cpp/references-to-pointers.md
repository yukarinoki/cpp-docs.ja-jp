---
description: 詳細については、「ポインターへの参照」を参照してください。
title: ポインターへの参照
ms.date: 06/13/2019
helpviewer_keywords:
- references, to pointers
ms.assetid: 4ce48b08-1511-4d2f-a31f-95f99eac0c70
ms.openlocfilehash: 5a554b6df4630a9772a5fceb9c51a9feaa9237d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252533"
---
# <a name="references-to-pointers"></a>ポインターへの参照

ポインターへの参照は、オブジェクトへの参照とほぼ同じ方法で宣言できます。 ポインターへの参照は、通常のポインターのように使用される変更可能な値です。

## <a name="example"></a>例

このコードサンプルは、ポインターへのポインターとポインターへの参照の使用の違いを示しています。

関数 `Add1` と関数 `Add2` は機能的に同等ですが、同じようには呼び出されません。 違いは、は `Add1` ダブル間接参照を使用しますが、 `Add2` ポインターへの参照の利便性を使用することです。

```cpp
// references_to_pointers.cpp
// compile with: /EHsc

#include <iostream>
#include <string>

// C++ Standard Library namespace
using namespace std;

enum {
   sizeOfBuffer = 132
};

// Define a binary tree structure.
struct BTree {
   char  *szText;
   BTree *Left;
   BTree *Right;
};

// Define a pointer to the root of the tree.
BTree *btRoot = 0;

int Add1( BTree **Root, char *szToAdd );
int Add2( BTree*& Root, char *szToAdd );
void PrintTree( BTree* btRoot );

int main( int argc, char *argv[] ) {
   // Usage message
   if( argc < 2 ) {
      cerr << "Usage: " << argv[0] << " [1 | 2]" << "\n";
      cerr << "\nwhere:\n";
      cerr << "1 uses double indirection\n";
      cerr << "2 uses a reference to a pointer.\n";
      cerr << "\nInput is from stdin. Use ^Z to terminate input.\n";
      return 1;
   }

   char *szBuf = new char[sizeOfBuffer];
   if (szBuf == NULL) {
      cerr << "Out of memory!\n";
      return -1;
   }

   // Read a text file from the standard input device and
   //  build a binary tree.
   while( !cin.eof() )
   {
      cin.get( szBuf, sizeOfBuffer, '\n' );
      cin.get();

      if ( strlen( szBuf ) ) {
         switch ( *argv[1] ) {
            // Method 1: Use double indirection.
            case '1':
               Add1( &btRoot, szBuf );
               break;
            // Method 2: Use reference to a pointer.
            case '2':
               Add2( btRoot, szBuf );
               break;
            default:
               cerr << "Illegal value '"
                  << *argv[1]
                  << "' supplied for add method.\n"
                     << "Choose 1 or 2.\n";
               return -1;
         }
      }
   }
   // Display the sorted list.
   PrintTree( btRoot );
}

// PrintTree: Display the binary tree in order.
void PrintTree( BTree* MybtRoot ) {
   // Traverse the left branch of the tree recursively.
   if ( MybtRoot->Left )
      PrintTree( MybtRoot->Left );

   // Print the current node.
   cout << MybtRoot->szText << "\n";

   // Traverse the right branch of the tree recursively.
   if ( MybtRoot->Right )
      PrintTree( MybtRoot->Right );
}

// Add1: Add a node to the binary tree.
//       Uses double indirection.
int Add1( BTree **Root, char *szToAdd ) {
   if ( (*Root) == 0 ) {
      (*Root) = new BTree;
      (*Root)->Left = 0;
      (*Root)->Right = 0;
      (*Root)->szText = new char[strlen( szToAdd ) + 1];
      strcpy_s((*Root)->szText, (strlen( szToAdd ) + 1), szToAdd );
      return 1;
   }
   else {
      if ( strcmp( (*Root)->szText, szToAdd ) > 0 )
         return Add1( &((*Root)->Left), szToAdd );
      else
         return Add1( &((*Root)->Right), szToAdd );
   }
}

// Add2: Add a node to the binary tree.
//       Uses reference to pointer
int Add2( BTree*& Root, char *szToAdd ) {
   if ( Root == 0 ) {
      Root = new BTree;
      Root->Left = 0;
      Root->Right = 0;
      Root->szText = new char[strlen( szToAdd ) + 1];
      strcpy_s( Root->szText, (strlen( szToAdd ) + 1), szToAdd );
      return 1;
   }
   else {
      if ( strcmp( Root->szText, szToAdd ) > 0 )
         return Add2( Root->Left, szToAdd );
      else
         return Add2( Root->Right, szToAdd );
   }
}
```

```Output
Usage: references_to_pointers.exe [1 | 2]

where:
1 uses double indirection
2 uses a reference to a pointer.

Input is from stdin. Use ^Z to terminate input.
```

## <a name="see-also"></a>関連項目

[参照](../cpp/references-cpp.md)
