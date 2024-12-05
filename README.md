def bucket_sort(arr):
    """
    Ordena uma lista usando o algoritmo Bucket Sort.

    :param arr: Lista de elementos a serem ordenados.
    :return: A lista ordenada.
    """
    if len(arr) == 0:
        return arr

    # Encontra o valor máximo e mínimo para determinar o intervalo dos buckets
    min_val, max_val = min(arr), max(arr)
    bucket_count = len(arr)  # Um bucket para cada elemento na média
    buckets = [[] for _ in range(bucket_count)]

    # Distribui os elementos nos buckets
    for num in arr:
        index = int(bucket_count * (num - min_val) / (max_val - min_val + 1))
        buckets[index].append(num)

    # Ordena individualmente cada bucket e concatena os resultados
    sorted_array = []
    for bucket in buckets:
        sorted_array.extend(sorted(bucket))  # Pode substituir por Insertion Sort

    return sorted_array


# Testes
if __name__ == "__main__":
    data = [0.78, 0.17, 0.39, 0.26, 0.72, 0.94, 0.21, 0.12, 0.23, 0.68]
    print("Lista original:", data)
    sorted_data = bucket_sort(data)
    print("Lista ordenada:", sorted_data)
# Bucket-Sort
