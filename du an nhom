def count_safe_squares(n, rooks):
    """
    Tính số ô an toàn trên bàn cờ n x n khi có các quân xe ở vị trí cho trước.
    
    Args:
        n: kích thước bàn cờ (n x n)
        rooks: danh sách các quân xe, mỗi quân xe là tuple (hàng, cột)
    
    Returns:
        Số ô an toàn (không bị tấn công bởi bất kỳ quân xe nào)
    """
    # 1. Khởi tạo các list để lưu hàng và cột bị tấn công
    unsafe_rows = []  # Lưu tất cả các hàng có quân xe
    unsafe_cols = []  # Lưu tất cả các cột có quân xe
    
    # 2. Duyệt qua từng quân xe để thu thập thông tin
    for rook in rooks:
        row, col = rook  # Lấy tọa độ hàng và cột của quân xe
        unsafe_rows.append(row)  # Thêm hàng này vào danh sách hàng bị tấn công
        unsafe_cols.append(col)  # Thêm cột này vào danh sách cột bị tấn công
    
    # 3. Sử dụng set để loại bỏ các hàng/cột trùng lặp
    #    (vì một hàng/cột có thể bị tấn công bởi nhiều quân xe)
    unique_unsafe_rows = set(unsafe_rows)  # Tập hợp các hàng bị tấn công (không trùng)
    unique_unsafe_cols = set(unsafe_cols)  # Tập hợp các cột bị tấn công (không trùng)
    
    # 4. Tính số hàng và cột an toàn
    safe_rows_count = n - len(unique_unsafe_rows)  # Số hàng không bị tấn công
    safe_cols_count = n - len(unique_unsafe_cols)  # Số cột không bị tấn công
    
    # 5. Số ô an toàn = (số hàng an toàn) × (số cột an toàn)
    #    Vì mỗi ô an toàn phải nằm trên cả hàng an toàn VÀ cột an toàn
    return safe_rows_count * safe_cols_count


# Test với các ví dụ từ đề bài
if __name__ == "__main__":
    # Test case 1
    result1 = count_safe_squares(10, [(2,3),(4,4)])
    print(f"Test 1: n=10, rooks=[(2,3),(4,4)] -> {result1} (expected: 64)")
    
    # Test case 2
    result2 = count_safe_squares(91, [(1,1),(4,4),(3,5),(0,7)])
    print(f"Test 2: n=91, rooks=[(1,1),(4,4),(3,5),(0,7)] -> {result2} (expected: 7569)")
    
    # Test case 3
    result3 = count_safe_squares(20, [(1,0),(3,6),(11,5),(1,2)])
    print(f"Test 3: n=20, rooks=[(1,0),(3,6),(11,5),(1,2)] -> {result3} (expected: 272)")
    
    # Test case 4
    result4 = count_safe_squares(7, [(0,2),(3,9),(3,4)])
    print(f"Test 4: n=7, rooks=[(0,2),(3,9),(3,4)] -> {result4} (expected: 20)")
