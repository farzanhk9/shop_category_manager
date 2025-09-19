# 🛍️ Simple Shop Category Manager

shop = {}

def add_category():
    category = input("Enter category name: ")
    if category in shop:
        print("⚠️ This category already exists.")
    else:
        shop[category] = []
        print(f"✅ Category '{category}' added.")

def add_product():
    category = input("Enter category name: ")
    if category not in shop:
        print("⚠️ Category not found. Please add category first.")
        return
    product = input("Enter product name: ")
    shop[category].append(product)
    print(f"✅ Product '{product}' added to category '{category}'.")

def list_categories():
    if not shop:
        print("📭 No categories yet.")
        return
    print("\n=== Categories ===")
    for cat, items in shop.items():
        print(f"- {cat} ({len(items)} products)")

def list_products():
    category = input("Enter category name: ")
    if category not in shop:
        print("⚠️ Category not found.")
        return
    print(f"\n📦 Products in '{category}':")
    for p in shop[category]:
        print(f"  • {p}")

def main():
    while True:
        print("\n=== SHOP CATEGORY MANAGER ===")
        print("1. Add category")
        print("2. Add product to category")
        print("3. List categories")
        print("4. List products in category")
        print("5. Exit")

        choice = input("Choose: ")
        if choice == "1":
            add_category()
        elif choice == "2":
            add_product()
        elif choice == "3":
            list_categories()
        elif choice == "4":
            list_products()
        elif choice == "5":
            print("👋 Exiting...")
            break
        else:
            print("⚠️ Invalid choice!")

if __name__ == "__main__":
    main()
