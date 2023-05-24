#include <iostream>
#include <vector>
#include <cmath>

std::vector<int> findBestCoordinate(std::vector<std::vector<int>>& towers, int radius) {
    int maxQuality = 0;
    std::vector<int> bestCoordinate = {0, 0};

    for (int x = 0; x <= 50; x++) { // Assuming the range of coordinates is from 0 to 50
        for (int y = 0; y <= 50; y++) {
            int quality = 0;

            for (const auto& tower : towers) {
                int xi = tower[0];
                int yi = tower[1];
                int qi = tower[2];

                double distance = std::sqrt(std::pow(xi - x, 2) + std::pow(yi - y, 2));

                if (distance <= radius) {
                    quality += qi / (1 + std::floor(distance));
                }
            }

            if (quality > maxQuality) {
                maxQuality = quality;
                bestCoordinate = {x, y};
            }
        }
    }

    return bestCoordinate;
}

int main() {
    std::vector<std::vector<int>> towers = {{1, 2, 5}, {2, 1, 7}, {3, 1, 9}};
    int radius = 5;

    std::vector<int> bestCoordinate = findBestCoordinate(towers, radius);

    std::cout << "Best Coordinate: (" << bestCoordinate[0] << ", " << bestCoordinate[1] << ")" << std::endl;

    return 0;
}



Input = [{1, 2, 5}, {2, 1, 7}, {3, 1, 9}]
Output = [2,1]
